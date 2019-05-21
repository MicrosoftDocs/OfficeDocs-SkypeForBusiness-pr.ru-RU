---
title: Настройка множества клиентов в пограничном контроллере сеансов
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Сведения о том, как настроить один межсеансовый контроллер (SBC) для обслуживания нескольких клиентов.
ms.openlocfilehash: 5392359307d97e010f86d3bb71f2f7c3f3d1ffb6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290471"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a><span data-ttu-id="9d813-103">Настройка множества клиентов в пограничном контроллере сеансов</span><span class="sxs-lookup"><span data-stu-id="9d813-103">Configure a Session Border Controller for multiple tenants</span></span>

<span data-ttu-id="9d813-104">Прямая маршрутизация поддерживает настройку одного межсеансового контроллера (SBC) для обслуживания нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="9d813-104">Direct Routing supports configuring one Session Border Controller (SBC) to serve multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="9d813-105">Этот сценарий предназначен для партнеров Майкрософт и/или PSTN-перевозчиков, которые называются перевозчиками позже в этом документе.</span><span class="sxs-lookup"><span data-stu-id="9d813-105">This scenario is designed for Microsoft partners and/or PSTN carriers, referred to as carriers later in this document.</span></span> <span data-ttu-id="9d813-106">Перевозчик, который продает услуги телефонной связи, доставляется своим клиентам в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9d813-106">A carrier sells telephony services delivered to Microsoft Teams to their customers.</span></span> 

<span data-ttu-id="9d813-107">Оператор:</span><span class="sxs-lookup"><span data-stu-id="9d813-107">A carrier:</span></span>
- <span data-ttu-id="9d813-108">Развертывает и управляет SBC в центре обработки данных (пользователи не обязаны реализовывать SBC, и они получают услуги телефонии от оператора перевозчика в клиенте Teams).</span><span class="sxs-lookup"><span data-stu-id="9d813-108">Deploys and manages an SBC in their datacenter (customers do not need to implement an SBC, and they receive telephony services from the carrier in the Teams client).</span></span>
- <span data-ttu-id="9d813-109">Подключает этот SBC к нескольким клиентам.</span><span class="sxs-lookup"><span data-stu-id="9d813-109">Interconnects the SBC to multiple tenants.</span></span>
- <span data-ttu-id="9d813-110">Предоставляет клиентам услуги PSTN.</span><span class="sxs-lookup"><span data-stu-id="9d813-110">Provides PSTN services to customers.</span></span>
- <span data-ttu-id="9d813-111">Управление качеством связи в конце.</span><span class="sxs-lookup"><span data-stu-id="9d813-111">Manages call quality end to end.</span></span>
- <span data-ttu-id="9d813-112">Плата за пользование услугами PSTN – отдельно.</span><span class="sxs-lookup"><span data-stu-id="9d813-112">Charges separately for PSTN services.</span></span>

<span data-ttu-id="9d813-113">Корпорация Майкрософт не управляет перевозчиками.</span><span class="sxs-lookup"><span data-stu-id="9d813-113">Microsoft does not manage carriers.</span></span> <span data-ttu-id="9d813-114">Корпорация Майкрософт предложит АТС (телефонная система Microsoft) и клиент Teams, удостоверяет телефоны и удостоверяет поучетную запись SBCs, которую можно использовать в телефонной системе Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9d813-114">Microsoft offers a PBX (Microsoft Phone System) and a Teams client, certifies phones, and certifies SBCs that can be used with the Microsoft Phone System.</span></span> <span data-ttu-id="9d813-115">Перед выбором оператора убедитесь в том, что ваш выбор имеет сертифицированный SBC и может управлять качеством звука в конце.</span><span class="sxs-lookup"><span data-stu-id="9d813-115">Before choosing a carrier, please ensure that your choice has a certified SBC and can manage voice quality end to end.</span></span>

<span data-ttu-id="9d813-116">Ниже приведены инструкции по настройке сценария в разделе Техническая реализация.</span><span class="sxs-lookup"><span data-stu-id="9d813-116">The following are the technical implementation steps to configure the scenario.</span></span>

<span data-ttu-id="9d813-117">**Только несущей:**</span><span class="sxs-lookup"><span data-stu-id="9d813-117">**Carrier only:**</span></span>
1. <span data-ttu-id="9d813-118">Разверните SBC и настройте его для сценария размещения в соответствии с инструкциями [от сертифицированных поставщиков SBC](#deploy-and-configure-the-sbc).</span><span class="sxs-lookup"><span data-stu-id="9d813-118">Deploy the SBC and configure it for the hosting scenario according to the [instructions from the certified SBC vendors](#deploy-and-configure-the-sbc).</span></span>
2. <span data-ttu-id="9d813-119">Зарегистрируйте имя базового домена в клиенте несущей и запросите сертификат с подстановочными знаками.</span><span class="sxs-lookup"><span data-stu-id="9d813-119">Register a base domain name in the carrier tenant and request a wildcard certificate.</span></span>
3. <span data-ttu-id="9d813-120">Регистрация поддомена для каждого клиента, который является частью базового домена.</span><span class="sxs-lookup"><span data-stu-id="9d813-120">Register a subdomain for every customer, which is part of the base domain.</span></span>

<span data-ttu-id="9d813-121">**Перевозчик с глобальным администратором клиента:**</span><span class="sxs-lookup"><span data-stu-id="9d813-121">**Carrier with a Customer Global Administrator:**</span></span>
1. <span data-ttu-id="9d813-122">Добавьте имя поддомена в клиент клиента.</span><span class="sxs-lookup"><span data-stu-id="9d813-122">Add the subdomain name to the customer tenant.</span></span>
2. <span data-ttu-id="9d813-123">Активация имени поддомена.</span><span class="sxs-lookup"><span data-stu-id="9d813-123">Activate the subdomain name.</span></span>
3. <span data-ttu-id="9d813-124">Настройте магистраль из несущей для клиента и подготовки пользователей.</span><span class="sxs-lookup"><span data-stu-id="9d813-124">Configure the trunk from the carrier to the customer tenant and provision users.</span></span>

<span data-ttu-id="9d813-125">*Убедитесь в том, что вы понимаете основы DNS и как это доменное имя управляется в Office 365. Ознакомьтесь [со статьей получение справки по доменам Office 365,](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) прежде чем продолжить работу.*</span><span class="sxs-lookup"><span data-stu-id="9d813-125">*Please make sure you understand DNS basics and how the domain name is managed in Office 365. Review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) before proceeding further.*</span></span>

## <a name="deploy-and-configure-the-sbc"></a><span data-ttu-id="9d813-126">Развертывание и настройка SBC</span><span class="sxs-lookup"><span data-stu-id="9d813-126">Deploy and configure the SBC</span></span>

<span data-ttu-id="9d813-127">Подробное описание процедуры развертывания и настройки SBCs для сценария размещения SBC можно найти в документации поставщика SBC.</span><span class="sxs-lookup"><span data-stu-id="9d813-127">For the detailed steps on how to deploy and configure SBCs for an SBC hosting scenario, please refer to the SBC vendor's documentation.</span></span>

- <span data-ttu-id="9d813-128">**AudioCodes:** [Заметки о настройке прямой маршрутизации](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams): Настройка сценария размещения SBC, описанного в разделе Подключение AudioCodesого SBC к Microsoft Teams, Настройка модели хостинга для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="9d813-128">**AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in “Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note.”</span></span> 
- <span data-ttu-id="9d813-129">**Связь на ленте:**  Сведения о том, как настроить одновременный SBCs-канал ленты и на эту страницу, можно найти в разделе [основы настройки SBC для ленты Microsoft](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) Teams [: Настройка направляющих для ОДНОнаправленных SBC Edge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span><span class="sxs-lookup"><span data-stu-id="9d813-129">**Ribbon Communications:**  Please refer to the [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) for documentation on how to configure Ribbon Core Series SBCs and to this page [Ribbon Best Practice - Configuring Carriers for Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span></span>

> [!NOTE]
> <span data-ttu-id="9d813-130">Обратите внимание на то, как настроить заголовок "Contact".</span><span class="sxs-lookup"><span data-stu-id="9d813-130">Please pay attention to how to configure the “Contact” header.</span></span> <span data-ttu-id="9d813-131">Заголовок контакта используется для поиска клиента клиента на входящем сообщении INVITE.</span><span class="sxs-lookup"><span data-stu-id="9d813-131">The Contact header is used to find the customer tenant on the incoming invite message.</span></span> 

## <a name="register-a-base-domain-and-subdomains"></a><span data-ttu-id="9d813-132">Регистрация базового домена и поддомены</span><span class="sxs-lookup"><span data-stu-id="9d813-132">Register a base domain and subdomains</span></span>

<span data-ttu-id="9d813-133">Для сценария размещения необходимо создать:</span><span class="sxs-lookup"><span data-stu-id="9d813-133">For the hosting scenario, you need to create:</span></span>
- <span data-ttu-id="9d813-134">Одно имя базового домена, принадлежащего перевозчику.</span><span class="sxs-lookup"><span data-stu-id="9d813-134">One base domain name owned by the carrier.</span></span>
- <span data-ttu-id="9d813-135">Поддомен, который является частью основного доменного имени в каждом клиенте клиента.</span><span class="sxs-lookup"><span data-stu-id="9d813-135">A subdomain that is part of the base domain name in every customer tenant.</span></span>

<span data-ttu-id="9d813-136">В приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="9d813-136">In the following example:</span></span>
- <span data-ttu-id="9d813-137">Адатум — это перевозчик, который обслуживает несколько клиентов, предоставляя доступ к Интернету и службам телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="9d813-137">Adatum is a carrier that serves several customers by providing Internet and telephony services.</span></span>
- <span data-ttu-id="9d813-138">Woodgrove Bank, Contoso и Adventure Works — это три клиента, у которых есть домены Office 365, но получать услуги телефонии от Адатум.</span><span class="sxs-lookup"><span data-stu-id="9d813-138">Woodgrove Bank, Contoso, and Adventure Works are three customers that have Office 365 domains but receive the telephony services from Adatum.</span></span>

<span data-ttu-id="9d813-139">Поддомены **должны** СОВПАДАТЬ с доменным именем канала, который будет настроен для клиента, и FQDN в заголовке контакта при отправке приглашения на Office 365.</span><span class="sxs-lookup"><span data-stu-id="9d813-139">Subdomains **MUST** match the FQDN name of the trunk that will be configured for the customer and the FQDN in the Contact header when sending the Invite to Office 365.</span></span> 

<span data-ttu-id="9d813-140">Когда звонок достигается в интерфейсе маршрутизации Office 365, интерфейс использует заголовок Contact (контакт) для поиска клиента, на котором необходимо искать пользователя.</span><span class="sxs-lookup"><span data-stu-id="9d813-140">When a call arrives at the Office 365 Direct Routing interface, the interface uses the Contact header to find the tenant where the user should be looked up.</span></span> <span data-ttu-id="9d813-141">Прямая маршрутизация не использует в приглашении Поиск номеров телефонов, так как некоторые клиенты могут иметь невыполненные номера, которые могут перекрываться в нескольких клиентах.</span><span class="sxs-lookup"><span data-stu-id="9d813-141">Direct Routing does not use phone number lookup on the Invite, as some customers might have non-DID numbers that can overlap in several tenants.</span></span> <span data-ttu-id="9d813-142">Таким образом, полное доменное имя в заголовке контакта требуется для определения точного клиента, который должен найти пользователя по номеру телефона.</span><span class="sxs-lookup"><span data-stu-id="9d813-142">Therefore, the FQDN name in the Contact header is required to identify the exact tenant to look up the user by the phone number.</span></span>

<span data-ttu-id="9d813-143">*Дополнительные сведения о создании доменных имен в клиентах Office 365 можно найти в [статьях получение справки о доменах office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*</span><span class="sxs-lookup"><span data-stu-id="9d813-143">*Please review  [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about creating domain names in Office 365 tenants.*</span></span>

<span data-ttu-id="9d813-144">На приведенной ниже схеме выводятся общие сведения о требованиях к базовому домену, дочерним доменам и заголовку контакта.</span><span class="sxs-lookup"><span data-stu-id="9d813-144">The following diagram summarizes the requirements to base domain, subdomains, and Contact header.</span></span>

![Требования к базовому домену, дочерним доменам и заголовку контакта](media/direct-routing-1-sbc-requirements.png)

<span data-ttu-id="9d813-146">Для использования SBC требуется сертификат для проверки подлинности подключений.</span><span class="sxs-lookup"><span data-stu-id="9d813-146">The SBC requires a certificate to authenticate the connections.</span></span> <span data-ttu-id="9d813-147">Для сценария размещения SBC-оператора необходимо запросить сертификат в сети SAN \* \*. басе_домаин (например \*, Customers.adatum.biz)\*.</span><span class="sxs-lookup"><span data-stu-id="9d813-147">For the SBC hosting scenario, the carrier needs to request a certificate with SAN *\*.base_domain (for example, \*customers.adatum.biz)*.</span></span> <span data-ttu-id="9d813-148">Этот сертификат можно использовать для проверки подлинности подключений к нескольким клиентам, обслуживаемым одним SBC.</span><span class="sxs-lookup"><span data-stu-id="9d813-148">This certificate can be used to authenticate connections to multiple tenants served from a single SBC.</span></span>

<span data-ttu-id="9d813-149">В приведенной ниже таблице показан пример одной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9d813-149">The following table is an example of one configuration.</span></span>


|<span data-ttu-id="9d813-150">Новое доменное имя</span><span class="sxs-lookup"><span data-stu-id="9d813-150">New domain name</span></span> |<span data-ttu-id="9d813-151">Тип</span><span class="sxs-lookup"><span data-stu-id="9d813-151">Type</span></span>|<span data-ttu-id="9d813-152">Пользователь</span><span class="sxs-lookup"><span data-stu-id="9d813-152">Registered</span></span>  |<span data-ttu-id="9d813-153">Сеть SAN сертификата для SBC</span><span class="sxs-lookup"><span data-stu-id="9d813-153">Certificate SAN for SBC</span></span>  |<span data-ttu-id="9d813-154">Домен по умолчанию клиента в примере</span><span class="sxs-lookup"><span data-stu-id="9d813-154">Tenant default domain in the example</span></span>  |<span data-ttu-id="9d813-155">Полное доменное имя, которое SBC должен присутствовать в заголовке контакта при отправке звонков пользователям</span><span class="sxs-lookup"><span data-stu-id="9d813-155">FQDN name that SBC must present in the Contact header when sending calls to users</span></span>|
|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="9d813-156">customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9d813-156">customers.adatum.biz</span></span>|    <span data-ttu-id="9d813-157">Основании</span><span class="sxs-lookup"><span data-stu-id="9d813-157">Base</span></span>     |     <span data-ttu-id="9d813-158">В клиенте несущей</span><span class="sxs-lookup"><span data-stu-id="9d813-158">In carrier tenant</span></span>  |    <span data-ttu-id="9d813-159">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9d813-159">\*.customers.adatum.biz</span></span>  |   <span data-ttu-id="9d813-160">adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9d813-160">adatum.biz</span></span>      |<span data-ttu-id="9d813-161">НД — это клиент службы, но не пользователи</span><span class="sxs-lookup"><span data-stu-id="9d813-161">NA, this is a service tenant, no users</span></span> |
|<span data-ttu-id="9d813-162">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9d813-162">sbc1.customers.adatum.biz</span></span>|    <span data-ttu-id="9d813-163">Поддомен</span><span class="sxs-lookup"><span data-stu-id="9d813-163">Subdomain</span></span>  |    <span data-ttu-id="9d813-164">В клиенте клиента</span><span class="sxs-lookup"><span data-stu-id="9d813-164">In a customer tenant</span></span>  |    <span data-ttu-id="9d813-165">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9d813-165">\*.customers.adatum.biz</span></span>  | <span data-ttu-id="9d813-166">woodgrovebank.us</span><span class="sxs-lookup"><span data-stu-id="9d813-166">woodgrovebank.us</span></span>  |  <span data-ttu-id="9d813-167">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9d813-167">sbc1.customers.adatum.biz</span></span>|
|<span data-ttu-id="9d813-168">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9d813-168">sbc2.customers.adatum.biz</span></span>  |   <span data-ttu-id="9d813-169">Поддомен</span><span class="sxs-lookup"><span data-stu-id="9d813-169">Subdomain</span></span> | <span data-ttu-id="9d813-170">В клиенте клиента</span><span class="sxs-lookup"><span data-stu-id="9d813-170">In a customer tenant</span></span>   |   <span data-ttu-id="9d813-171">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9d813-171">\*.customers.adatum.biz</span></span>   |<span data-ttu-id="9d813-172">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d813-172">contoso.com</span></span>   |<span data-ttu-id="9d813-173">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9d813-173">sbc2.customers.adatum.biz</span></span> |
|<span data-ttu-id="9d813-174">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9d813-174">sbc3.customers.adatum.biz</span></span> |   <span data-ttu-id="9d813-175">Поддомен</span><span class="sxs-lookup"><span data-stu-id="9d813-175">Subdomain</span></span> | <span data-ttu-id="9d813-176">В клиенте клиента</span><span class="sxs-lookup"><span data-stu-id="9d813-176">In a customer tenant</span></span> |   <span data-ttu-id="9d813-177">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9d813-177">\*.customers.adatum.biz</span></span>  |  <span data-ttu-id="9d813-178">adventureworks.com</span><span class="sxs-lookup"><span data-stu-id="9d813-178">adventureworks.com</span></span> | <span data-ttu-id="9d813-179">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9d813-179">sbc3.customers.adatum.biz</span></span> |
||         |         |         |         |         |

<span data-ttu-id="9d813-180">Чтобы настроить базовые и дочерние домены, выполните действия, описанные ниже.</span><span class="sxs-lookup"><span data-stu-id="9d813-180">To configure the base and subdomains, please follow the steps described below.</span></span> <span data-ttu-id="9d813-181">В этом примере мы назначением базового доменного имени (customers.adatum.biz) и поддоменом для одного клиента (sbc1.customers.adatum.biz в клиенте Woodgrove Bank).</span><span class="sxs-lookup"><span data-stu-id="9d813-181">In the example, we will configure a base domain name (customers.adatum.biz) and a subdomain for one customer (sbc1.customers.adatum.biz in Woodgrove Bank tenant).</span></span>

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a><span data-ttu-id="9d813-182">Регистрация базового доменного имени в клиенте перевозчика</span><span class="sxs-lookup"><span data-stu-id="9d813-182">Register a base domain name in the carrier tenant</span></span>

<span data-ttu-id="9d813-183">**Эти действия выполняются в клиенте перевозчика.**</span><span class="sxs-lookup"><span data-stu-id="9d813-183">**These actions are performed in the carrier tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a><span data-ttu-id="9d813-184">Убедитесь, что у вас есть соответствующие права в клиенте перевозчика.</span><span class="sxs-lookup"><span data-stu-id="9d813-184">Ensure that you have appropriate rights in the carrier tenant</span></span>

<span data-ttu-id="9d813-185">Вы можете добавлять новые домены только в том случае, если вы вошли в центр администрирования Microsoft 365 как глобальный администратор.</span><span class="sxs-lookup"><span data-stu-id="9d813-185">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="9d813-186">Чтобы проверить, есть ли у вас роль, войдите в центр администрирования Microsoft 365https://portal.office.com)(выберите "**Активные пользователи** **пользователей** > " и убедитесь в том, что у вас есть роль глобального администратора).</span><span class="sxs-lookup"><span data-stu-id="9d813-186">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="9d813-187">Дополнительные сведения о ролях администратора и назначение роли в Office 365 можно найти в разделе [о ролях администратора office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span><span class="sxs-lookup"><span data-stu-id="9d813-187">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a><span data-ttu-id="9d813-188">Добавление базового домена в клиент и его проверка</span><span class="sxs-lookup"><span data-stu-id="9d813-188">Add a base domain to the tenant and verify it</span></span>

1.  <span data-ttu-id="9d813-189">В центре администрирования Microsoft 365 перейдите в раздел**домены** >  **настройки** > **Добавить домен**.</span><span class="sxs-lookup"><span data-stu-id="9d813-189">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2.  <span data-ttu-id="9d813-190">В поле **введите домен, которым вы владеете** , введите полное доменное имя базового домена.</span><span class="sxs-lookup"><span data-stu-id="9d813-190">In the **Enter a domain you own** box, type the FQDN of the base domain.</span></span> <span data-ttu-id="9d813-191">В приведенном ниже примере базовым доменом является *Customers.adatum.biz*.</span><span class="sxs-lookup"><span data-stu-id="9d813-191">In the following example, the base domain is *customers.adatum.biz*.</span></span>

    ![Добавление базового домена](media/direct-routing-2-sbc-add-domain.png)

3. <span data-ttu-id="9d813-193">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9d813-193">Click **Next**.</span></span>
4. <span data-ttu-id="9d813-194">В примере клиент уже имеет adatum.biz в качестве проверенного доменного имени.</span><span class="sxs-lookup"><span data-stu-id="9d813-194">In the example, the tenant already has adatum.biz as a verified domain name.</span></span> <span data-ttu-id="9d813-195">Мастер не запрашивает дополнительной проверки, так как customers.adatum.biz является поддоменом для уже зарегистрированного имени.</span><span class="sxs-lookup"><span data-stu-id="9d813-195">The wizard will not ask for additional verification because customers.adatum.biz is a subdomain for the already registered name.</span></span> <span data-ttu-id="9d813-196">Однако если вы добавите полное доменное имя, которое еще не прошло проверку, вам нужно будет пройти процесс проверки.</span><span class="sxs-lookup"><span data-stu-id="9d813-196">However, if you add an FQDN that has not been verified before, you will need to go through the process of verification.</span></span> <span data-ttu-id="9d813-197">Процесс проверки [описан ниже](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span><span class="sxs-lookup"><span data-stu-id="9d813-197">The process of verification is [described below](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span></span>

    ![Подтверждение проверенного доменного имени](media/direct-routing-3-sbc-verify-domain.png)

5.  <span data-ttu-id="9d813-199">Нажмите кнопку **Далее**, а затем на странице **обновления параметров DNS** выберите **я добавляю записи DNS самостоятельно** и нажимаю кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9d813-199">Click **Next**, and on the **Update DNS Settings** page, select **I’ll add the DNS records myself** and click **Next**.</span></span>
6.  <span data-ttu-id="9d813-200">На следующей странице удалите все значения (если вы не хотите использовать доменное имя Exchange, SharePoint или Teams/Skype для бизнеса), нажмите кнопку **Далее**, а затем — **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9d813-200">On the next page, clear all values (unless you want to use the domain name for Exchange, SharePoint, or Teams/Skype for Business), click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="9d813-201">Убедитесь, что новый домен находится в состоянии "завершить установку".</span><span class="sxs-lookup"><span data-stu-id="9d813-201">Make sure your new domain is in the Setup complete status.</span></span>

    ![Домены, показывающие состояние настройки завершено](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a><span data-ttu-id="9d813-203">Активация доменного имени</span><span class="sxs-lookup"><span data-stu-id="9d813-203">Activate the domain name</span></span>

<span data-ttu-id="9d813-204">После того как вы зарегистрируете доменное имя, вам нужно активировать его, добавив по крайней мере один лицензированный пользователь E1, E3 или "число пользователей" и указав адрес SIP с полным доменным именем, соответствующим созданному базовому домену.</span><span class="sxs-lookup"><span data-stu-id="9d813-204">After you have registered a domain name, you need to activate it by adding at least one E1, E3, or E5 licensed user and assigning a SIP address with the FQDN portion of the SIP address matching the created base domain.</span></span> 

<span data-ttu-id="9d813-205">*Дополнительные сведения о добавлении пользователей в клиентах Office 365 можно найти в [статьях получение справки о доменах office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*</span><span class="sxs-lookup"><span data-stu-id="9d813-205">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="9d813-206">Например: test@customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9d813-206">For example: test@customers.adatum.biz</span></span>

![Страница активации базового домена](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a><span data-ttu-id="9d813-208">Регистрация имени поддомена в клиенте клиента</span><span class="sxs-lookup"><span data-stu-id="9d813-208">Register a subdomain name in a customer tenant</span></span>

<span data-ttu-id="9d813-209">Вам потребуется создать уникальное имя поддомена для каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="9d813-209">You will need to create a unique subdomain name for every customer.</span></span> <span data-ttu-id="9d813-210">В этом примере создается поддомен sbc1.customers.adatum.biz в клиенте с именем домена по умолчанию woodgrovebank.us.</span><span class="sxs-lookup"><span data-stu-id="9d813-210">In this example, we will create a subdomain sbc1.customers.adatum.biz in a tenant with the default domain name woodgrovebank.us.</span></span>

<span data-ttu-id="9d813-211">**Все действия, описанные ниже, находятся в клиенте клиента.**</span><span class="sxs-lookup"><span data-stu-id="9d813-211">**All actions below are in the customer tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a><span data-ttu-id="9d813-212">Убедитесь, что у вас есть соответствующие права в клиенте клиента</span><span class="sxs-lookup"><span data-stu-id="9d813-212">Ensure that you have appropriate rights in the customer tenant</span></span>

<span data-ttu-id="9d813-213">Вы можете добавлять новые домены только в том случае, если вы вошли в центр администрирования Microsoft 365 как глобальный администратор.</span><span class="sxs-lookup"><span data-stu-id="9d813-213">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="9d813-214">Чтобы проверить, есть ли у вас роль, войдите в центр администрирования Microsoft 365https://portal.office.com)(выберите "**Активные пользователи** **пользователей** > " и убедитесь в том, что у вас есть роль глобального администратора).</span><span class="sxs-lookup"><span data-stu-id="9d813-214">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="9d813-215">Дополнительные сведения о ролях администратора и назначение роли в Office 365 можно найти в разделе [о ролях администратора office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span><span class="sxs-lookup"><span data-stu-id="9d813-215">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a><span data-ttu-id="9d813-216">Добавление поддомена в клиент клиента и его проверка</span><span class="sxs-lookup"><span data-stu-id="9d813-216">Add a subdomain to the customer tenant and verify it</span></span>
1. <span data-ttu-id="9d813-217">В центре администрирования Microsoft 365 перейдите в раздел**домены** >  **настройки** > **Добавить домен**.</span><span class="sxs-lookup"><span data-stu-id="9d813-217">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="9d813-218">В поле **введите домен, которым вы владеете** , введите полное доменное имя поддомена для этого клиента.</span><span class="sxs-lookup"><span data-stu-id="9d813-218">In the **Enter a domain you own** box, type the FQDN of the subdomain for this tenant.</span></span> <span data-ttu-id="9d813-219">В приведенном ниже примере поддомен является sbc1.customers.adatum.biz.</span><span class="sxs-lookup"><span data-stu-id="9d813-219">In the example below, the subdomain is sbc1.customers.adatum.biz.</span></span>

    ![Добавление поддомена клиента](media/direct-routing-5-sbc-add-customer-domain.png)

3. <span data-ttu-id="9d813-221">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9d813-221">Click **Next**.</span></span>
4. <span data-ttu-id="9d813-222">Полное доменное имя не было зарегистрировано в клиенте.</span><span class="sxs-lookup"><span data-stu-id="9d813-222">The FQDN has never been registered in the tenant.</span></span> <span data-ttu-id="9d813-223">На следующем этапе необходимо подтвердить домен.</span><span class="sxs-lookup"><span data-stu-id="9d813-223">In the next step, you will need to verify the domain.</span></span> <span data-ttu-id="9d813-224">**Вместо этого выберите Добавить запись TXT**.</span><span class="sxs-lookup"><span data-stu-id="9d813-224">Select **Add a TXT record instead**.</span></span> 

    ![Параметры на странице "Проверка домена"](media/direct-routing-6-sbc-verify-customer-domain.png)

5. <span data-ttu-id="9d813-226">Нажмите кнопку **Далее**и запишите значение txt, созданное для проверки имени домена.</span><span class="sxs-lookup"><span data-stu-id="9d813-226">Click **Next**, and note the TXT value generated to verify the domain name.</span></span>

    ![Текстовые записи на странице "Проверка домена"](media/direct-routing-7-sbc-verify-domain-txt.png)

6. <span data-ttu-id="9d813-228">Создайте запись TXT со значением, полученным на предыдущем этапе поставщика услуг размещения DNS оператора.</span><span class="sxs-lookup"><span data-stu-id="9d813-228">Create the TXT record with the value from the previous step in carrier’s DNS hosting provider.</span></span>

    ![Создание записи TXT в поставщике услуг размещения DNS оператора](media/direct-routing-8-sbc-txt-record.png)

    <span data-ttu-id="9d813-230">Дополнительные сведения можно найти в статье [Создание записей DNS для любого поставщика услуг размещения DNS для Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span><span class="sxs-lookup"><span data-stu-id="9d813-230">For more information, refer to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span></span>

7. <span data-ttu-id="9d813-231">Вернитесь в центр администрирования Microsoft 365 и нажмите кнопку " **проверить**".</span><span class="sxs-lookup"><span data-stu-id="9d813-231">Go back to the customer's Microsoft 365 admin center and click **Verify**.</span></span> 
8. <span data-ttu-id="9d813-232">На следующей странице выберите **я добавляю записи DNS самостоятельно** и нажимаю кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9d813-232">On the next page, select **I’ll add the DNS records myself** and click **Next**.</span></span>

    ![Параметры на странице обновления параметров DNS](media/direct-routing-9-sbc-update-dns.png)

9. <span data-ttu-id="9d813-234">На странице **Выбор Интернет-служб** снимите флажок все параметры и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9d813-234">On the **Choose your online services** page, clear all options and click **Next**.</span></span>

    ![Страница "выбор Интернет-служб"](media/direct-routing-10-sbc-choose-services.png)

10. <span data-ttu-id="9d813-236">На странице **Обновление параметров DNS** нажмите кнопку **Готово** .</span><span class="sxs-lookup"><span data-stu-id="9d813-236">Click **Finish** on the **Update DNS settings** page.</span></span>

    ![Страница обновления параметров DNS](media/direct-routing-11-sbc-update-dns-finish.png)

11. <span data-ttu-id="9d813-238">Убедитесь, что состояние задано как " **Настройка**".</span><span class="sxs-lookup"><span data-stu-id="9d813-238">Ensure that the status is **Setup complete**.</span></span> 
    
    ![Страница, показывающая состояние завершения настройки](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a><span data-ttu-id="9d813-240">Активация имени поддомена</span><span class="sxs-lookup"><span data-stu-id="9d813-240">Activate the subdomain name</span></span>

<span data-ttu-id="9d813-241">После регистрации доменного имени необходимо активировать его, добавив по крайней мере одного пользователя и указав адрес SIP с полным доменным именем SIP, соответствующим созданному поддомену в клиенте.</span><span class="sxs-lookup"><span data-stu-id="9d813-241">After you register a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created subdomain in the customer tenant.</span></span>

<span data-ttu-id="9d813-242">*Дополнительные сведения о добавлении пользователей в клиентах Office 365 можно найти в [статьях получение справки о доменах office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*</span><span class="sxs-lookup"><span data-stu-id="9d813-242">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="9d813-243">Например: test@sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9d813-243">For example: test@sbc1.customers.adatum.biz</span></span>

![Активация страницы поддомена](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a><span data-ttu-id="9d813-245">Создание магистрали и подготовка пользователей</span><span class="sxs-lookup"><span data-stu-id="9d813-245">Create a trunk and provision users</span></span>

> [!NOTE]
> <span data-ttu-id="9d813-246">В соответствии с отзывом, полученным в рамках программы внедрения, корпорация Майкрософт может изменить процесс создания магистральных каналов в клиентских клиентах для упрощения процесса.</span><span class="sxs-lookup"><span data-stu-id="9d813-246">Based on feedback we received in the Technical Adoption Program, Microsoft might change the process of creating trunks in the customer tenants to simplify the process.</span></span> <span data-ttu-id="9d813-247">Пожалуйста, ознакомьтесь с обновлениями документации на этой странице и следуйте техническим рекомендациям для получения дополнительных сведений в блогах сообщества Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9d813-247">Please watch the documentation updates on this page and follow the Microsoft Technical Community blogs for further information.</span></span> 

<span data-ttu-id="9d813-248">Создайте магистраль в домене клиента с помощью команды New-Ксонлинепстнгатевай.</span><span class="sxs-lookup"><span data-stu-id="9d813-248">Create a trunk in the customer domain using the New-CSonlinePSTNGateway command.</span></span> <span data-ttu-id="9d813-249">Полное доменное имя магистральной магистрали **должно** соответствовать поддоменом, созданному для клиента.</span><span class="sxs-lookup"><span data-stu-id="9d813-249">The trunk FQDN **MUST** match the subdomain created for the customer.</span></span>

<span data-ttu-id="9d813-250">Например:</span><span class="sxs-lookup"><span data-stu-id="9d813-250">For example:</span></span>

```
New-CSOnlinePSTNGateway –FQDN sbc1.customers.adatum.biz -SipSignallingPort 5068
```

<span data-ttu-id="9d813-251">При создании магистральной магистрали может появиться следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="9d813-251">When creating the trunk, you may receive the following error message:</span></span>

```
Can not use the "sbc1.customers.adatum.biz" domain as it was not configured for this tenant.
```

<span data-ttu-id="9d813-252">Дождитесь, пока регистрация домена и активация не попытаются выполнить репликацию, и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="9d813-252">Please allow some time for domain registration and activation to replicate and try again.</span></span>

<span data-ttu-id="9d813-253">Подготовьте пользователей к работе с телефонными номерами и настройте голосовой маршрут.</span><span class="sxs-lookup"><span data-stu-id="9d813-253">Provision users with the phone numbers and configure voice routing.</span></span>

<span data-ttu-id="9d813-254">Дополнительные сведения о новых возможностях Ксонлинепстнгатевай, подготовки пользователей и настройке голосовой маршрутизации можно найти в разделе [Настройка прямого маршрута](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="9d813-254">For more information on the New-CSOnlinePSTNGateway, provisioning users, and configuring voice routing, please refer to [Configure Direct Routing](direct-routing-configure.md).</span></span>


<span data-ttu-id="9d813-255">Пожалуйста, ознакомьтесь с [инструкциями поставщика SBC](#deploy-and-configure-the-sbc) о настройке отправки доменного имени поддомены в заголовке контакта.</span><span class="sxs-lookup"><span data-stu-id="9d813-255">Please refer to the [SBC vendor instructions](#deploy-and-configure-the-sbc) on configuring sending the FQDN name of subdomains in the Contact header.</span></span>

