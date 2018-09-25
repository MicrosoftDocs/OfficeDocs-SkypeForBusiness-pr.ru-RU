---
title: Настройте пограничный контроллер сеансов для нескольких клиентов
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Сведения о настройке одного пограничный контроллер сеансов (SBC) для обслуживания нескольких клиентов.
ms.openlocfilehash: 292a3e675455d112fdade04018e670b9a5f9c38f
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "25013427"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a><span data-ttu-id="d04a6-103">Настройте пограничный контроллер сеансов для нескольких клиентов</span><span class="sxs-lookup"><span data-stu-id="d04a6-103">Configure a Session Border Controller for multiple tenants</span></span>

<span data-ttu-id="d04a6-104">Прямое маршрутизации поддерживает Настройка одного пограничный контроллер сеансов (SBC) для обслуживания нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="d04a6-104">Direct Routing supports configuring one Session Border Controller (SBC) to serve multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="d04a6-105">Этот сценарий предназначен для партнеров Майкрософт и/или линии ТСОП, называется связи далее в этом документе.</span><span class="sxs-lookup"><span data-stu-id="d04a6-105">This scenario is designed for Microsoft partners and/or PSTN carriers, referred to as carriers later in this document.</span></span> <span data-ttu-id="d04a6-106">Поставщика продает служб телефонии доставлено группами Майкрософт своим клиентам.</span><span class="sxs-lookup"><span data-stu-id="d04a6-106">A carrier sells telephony services delivered to Microsoft Teams to their customers.</span></span> 

<span data-ttu-id="d04a6-107">Транспортная компания:</span><span class="sxs-lookup"><span data-stu-id="d04a6-107">A carrier:</span></span>
- <span data-ttu-id="d04a6-108">Развертывает и управляет SBC в их центра обработки данных (пользователям необходимо реализовать SBC и они получают службы телефонной связи с передающую в клиенте команды).</span><span class="sxs-lookup"><span data-stu-id="d04a6-108">Deploys and manages an SBC in their datacenter (customers do not need to implement an SBC, and they receive telephony services from the carrier in the Teams client).</span></span>
- <span data-ttu-id="d04a6-109">Соединения SBC к нескольким клиентам.</span><span class="sxs-lookup"><span data-stu-id="d04a6-109">Interconnects the SBC to multiple tenants.</span></span>
- <span data-ttu-id="d04a6-110">Предоставляет службы ТСОП для клиентов.</span><span class="sxs-lookup"><span data-stu-id="d04a6-110">Provides PSTN services to customers.</span></span>
- <span data-ttu-id="d04a6-111">Управляет качества звонка сквозного.</span><span class="sxs-lookup"><span data-stu-id="d04a6-111">Manages call quality end to end.</span></span>
- <span data-ttu-id="d04a6-112">Расходы отдельно для служб PSTN.</span><span class="sxs-lookup"><span data-stu-id="d04a6-112">Charges separately for PSTN services.</span></span>

<span data-ttu-id="d04a6-113">Корпорация Майкрософт не управляет связи.</span><span class="sxs-lookup"><span data-stu-id="d04a6-113">Microsoft does not manage carriers.</span></span> <span data-ttu-id="d04a6-114">Microsoft предлагает УАТС (телефонной системой Microsoft) и групп клиента, удостоверяет телефоны и подтверждает их изготовителей, которые могут использоваться с телефонной системой Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d04a6-114">Microsoft offers a PBX (Microsoft Phone System) and a Teams client, certifies phones, and certifies SBCs that can be used with the Microsoft Phone System.</span></span> <span data-ttu-id="d04a6-115">Перед выбором поставщика, убедитесь, что выбор имеет сертифицированного SBC и могут управлять качества голосовой связи сквозного.</span><span class="sxs-lookup"><span data-stu-id="d04a6-115">Before choosing a carrier, please ensure that your choice has a certified SBC and can manage voice quality end to end.</span></span>

<span data-ttu-id="d04a6-116">Ниже приведены технического внедрения действий по настройке в сценарии.</span><span class="sxs-lookup"><span data-stu-id="d04a6-116">The following are the technical implementation steps to configure the scenario.</span></span>

<span data-ttu-id="d04a6-117">**Поставщика:**</span><span class="sxs-lookup"><span data-stu-id="d04a6-117">**Carrier only:**</span></span>
1. <span data-ttu-id="d04a6-118">Развертывание SBC и настроить его для размещения сценария согласно [инструкциям из сертифицированными поставщиками SBC](#deploy-and-configure-the-sbc).</span><span class="sxs-lookup"><span data-stu-id="d04a6-118">Deploy the SBC and configure it for the hosting scenario according to the [instructions from the certified SBC vendors](#deploy-and-configure-the-sbc).</span></span>
2. <span data-ttu-id="d04a6-119">Регистрация имени базового домена в поставщика для клиентов и запросить сертификат подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="d04a6-119">Register a base domain name in the carrier tenant and request a wildcard certificate.</span></span>
3. <span data-ttu-id="d04a6-120">Зарегистрируйте дочернего домена для каждого клиента, которая является частью базового домена.</span><span class="sxs-lookup"><span data-stu-id="d04a6-120">Register a subdomain for every customer, which is part of the base domain.</span></span>

<span data-ttu-id="d04a6-121">**Поставщика с глобальным администратором клиента:**</span><span class="sxs-lookup"><span data-stu-id="d04a6-121">**Carrier with a Customer Global Administrator:**</span></span>
1. <span data-ttu-id="d04a6-122">Добавьте имя дочернего домена к клиенту клиента.</span><span class="sxs-lookup"><span data-stu-id="d04a6-122">Add the subdomain name to the customer tenant.</span></span>
2. <span data-ttu-id="d04a6-123">Активируйте имя дочернего домена.</span><span class="sxs-lookup"><span data-stu-id="d04a6-123">Activate the subdomain name.</span></span>
3. <span data-ttu-id="d04a6-124">Настройка магистрали из транспортной для клиента клиента и подготовки пользователей.</span><span class="sxs-lookup"><span data-stu-id="d04a6-124">Configure the trunk from the carrier to the customer tenant and provision users.</span></span>

<span data-ttu-id="d04a6-125">*Чтобы убедиться, что вам знакомы основные сведения о DNS и управлении имя домена в Office 365. Просмотрите [Получение справки по работе с Office 365 домены](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) перед продолжением работы необходимо.*</span><span class="sxs-lookup"><span data-stu-id="d04a6-125">*Please make sure you understand DNS basics and how the domain name is managed in Office 365. Review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) before proceeding further.*</span></span>

## <a name="deploy-and-configure-the-sbc"></a><span data-ttu-id="d04a6-126">Развертывание и настройка SBC</span><span class="sxs-lookup"><span data-stu-id="d04a6-126">Deploy and configure the SBC</span></span>

<span data-ttu-id="d04a6-127">Подробное описание действий по развернуть и настроить их изготовителей размещения случае SBC обратитесь к документации разработчика SBC.</span><span class="sxs-lookup"><span data-stu-id="d04a6-127">For the detailed steps on how to deploy and configure SBCs for an SBC hosting scenario, please refer to the SBC vendor's documentation.</span></span>

- <span data-ttu-id="d04a6-128">**AudioCodes:** [Заметки о конфигурации прямой маршрутизации](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), конфигурации SBC, размещения сценария, описанного в «Подключение SBC AudioCodes группами Майкрософт прямой маршрутизации размещение модели конфигурации уведомление».</span><span class="sxs-lookup"><span data-stu-id="d04a6-128">**AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in “Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note.”</span></span> 
- <span data-ttu-id="d04a6-129">**Ленты коммуникаций:**  Обратитесь за помощью для [Ленты Communications SBC ядра Microsoft группами руководство по настройке](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) для получения сведений о настройке ленты основных серии SBC и на этой странице [ленты наиболее рекомендация - Настройка доставки прямой маршрутизации Microsoft групп SBC Edge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span><span class="sxs-lookup"><span data-stu-id="d04a6-129">**Ribbon Communications:**  Please refer to the [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) for documentation on how to configure Ribbon Core Series SBCs and to this page [Ribbon Best Best Practice - Configuring Carriers for Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span></span>

> [!NOTE]
> <span data-ttu-id="d04a6-130">Пожалуйста, обратите внимание на способы настройки заголовка «Контакт».</span><span class="sxs-lookup"><span data-stu-id="d04a6-130">Please pay attention to how to configure the “Contact” header.</span></span> <span data-ttu-id="d04a6-131">Заголовок контакт будет использоваться для поиска клиента клиента во входящем сообщении пригласить.</span><span class="sxs-lookup"><span data-stu-id="d04a6-131">The Contact header is used to find the customer tenant on the incoming invite message.</span></span> 

## <a name="register-a-base-domain-and-subdomains"></a><span data-ttu-id="d04a6-132">Регистрация базового домен и дочерние домены</span><span class="sxs-lookup"><span data-stu-id="d04a6-132">Register a base domain and subdomains</span></span>

<span data-ttu-id="d04a6-133">Для размещения сценария необходимо создать:</span><span class="sxs-lookup"><span data-stu-id="d04a6-133">For the hosting scenario, you need to create:</span></span>
- <span data-ttu-id="d04a6-134">Один базовый доменное имя, принадлежащие оператор.</span><span class="sxs-lookup"><span data-stu-id="d04a6-134">One base domain name owned by the carrier.</span></span>
- <span data-ttu-id="d04a6-135">Дочерний домен, который является частью базового доменное имя в каждом клиента для клиентов.</span><span class="sxs-lookup"><span data-stu-id="d04a6-135">A subdomain that is part of the base domain name in every customer tenant.</span></span>

<span data-ttu-id="d04a6-136">В следующем примере:</span><span class="sxs-lookup"><span data-stu-id="d04a6-136">In the following example:</span></span>
- <span data-ttu-id="d04a6-137">Adatum является оператору, который обслуживает несколько клиентов, обеспечивающих работу служб Интернета и телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="d04a6-137">Adatum is a carrier that serves several customers by providing Internet and telephony services.</span></span>
- <span data-ttu-id="d04a6-138">Банка Woodgrove, Contoso и Adventure Works, трех клиентов, которые домены Office 365, но получают службы телефонной связи с Adatum.</span><span class="sxs-lookup"><span data-stu-id="d04a6-138">Woodgrove Bank, Contoso, and Adventure Works are three customers that have Office 365 domains but receive the telephony services from Adatum.</span></span>

<span data-ttu-id="d04a6-139">Дочерние домены, **должно** совпадать с именем полное доменное имя линии связи, которые будут настроены для клиента и полное доменное имя в заголовке контактов при отправке приглашения в Office 365.</span><span class="sxs-lookup"><span data-stu-id="d04a6-139">Subdomains **MUST** match the FQDN name of the trunk that will be configured for the customer and the FQDN in the Contact header when sending the Invite to Office 365.</span></span> 

<span data-ttu-id="d04a6-140">При поступлении вызова в интерфейсе прямой маршрутизации Office 365, интерфейс использует заголовок контакта для поиска клиента, где пользователь должен выполняться поиск.</span><span class="sxs-lookup"><span data-stu-id="d04a6-140">When a call arrives at the Office 365 Direct Routing interface, the interface uses the Contact header to find the tenant where the user should be looked up.</span></span> <span data-ttu-id="d04a6-141">Прямое маршрутизации не использует поиск номера телефона в приглашении, как некоторые клиенты могут быть не-БЫЛИ числа, можете пересекаются в нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="d04a6-141">Direct Routing does not use phone number lookup on the Invite, as some customers might have non-DID numbers that can overlap in several tenants.</span></span> <span data-ttu-id="d04a6-142">Таким образом полное ДОМЕННОЕ имя в заголовке контакт необходимо определить точное клиента для поиска пользователя по номеру телефона.</span><span class="sxs-lookup"><span data-stu-id="d04a6-142">Therefore, the FQDN name in the Contact header is required to identify the exact tenant to look up the user by the phone number.</span></span>

<span data-ttu-id="d04a6-143">*Ознакомьтесь с [Получение справки по работе с Office 365 домены](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) Дополнительные сведения о создании доменных имен в клиентов Office 365.*</span><span class="sxs-lookup"><span data-stu-id="d04a6-143">*Please review  [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about creating domain names in Office 365 tenants.*</span></span>

<span data-ttu-id="d04a6-144">На следующей диаграмме представлена требования для базового домена, поддомены и заголовок контакта.</span><span class="sxs-lookup"><span data-stu-id="d04a6-144">The following diagram summarizes the requirements to base domain, subdomains, and Contact header.</span></span>

![Требования для базового домена, поддомены и заголовок контакта](media/direct-routing-1-sbc-requirements.png)

<span data-ttu-id="d04a6-146">SBC требуется сертификат для проверки подлинности подключений.</span><span class="sxs-lookup"><span data-stu-id="d04a6-146">The SBC requires a certificate to authenticate the connections.</span></span> <span data-ttu-id="d04a6-147">Для размещения сценария SBC, передающую необходимо запросить сертификат с помощью альтернативного имени СУБЪЕКТА \* \*.base_domain (например, \*customers.adatum.biz)\*.</span><span class="sxs-lookup"><span data-stu-id="d04a6-147">For the SBC hosting scenario, the carrier needs to request a certificate with SAN *\*.base_domain (for example, \*customers.adatum.biz)*.</span></span> <span data-ttu-id="d04a6-148">Этот сертификат можно использовать для проверки подлинности подключений к нескольким клиентам, полученном из одного SBC.</span><span class="sxs-lookup"><span data-stu-id="d04a6-148">This certificate can be used to authenticate connections to multiple tenants served from a single SBC.</span></span>

<span data-ttu-id="d04a6-149">В следующей таблице приведен пример одной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d04a6-149">The following table is an example of one configuration.</span></span>


|<span data-ttu-id="d04a6-150">Новое доменное имя</span><span class="sxs-lookup"><span data-stu-id="d04a6-150">New domain name</span></span> |<span data-ttu-id="d04a6-151">Тип</span><span class="sxs-lookup"><span data-stu-id="d04a6-151">Type</span></span>|<span data-ttu-id="d04a6-152">Зарегистрирована</span><span class="sxs-lookup"><span data-stu-id="d04a6-152">Registered</span></span>  |<span data-ttu-id="d04a6-153">Сертификат SAN для SBC</span><span class="sxs-lookup"><span data-stu-id="d04a6-153">Certificate SAN for SBC</span></span>  |<span data-ttu-id="d04a6-154">Домен по умолчанию клиента в примере</span><span class="sxs-lookup"><span data-stu-id="d04a6-154">Tenant default domain in the example</span></span>  |<span data-ttu-id="d04a6-155">Полное ДОМЕННОЕ имя, которое необходимо представить SBC в заголовке контакт при отправке вызовов для пользователей</span><span class="sxs-lookup"><span data-stu-id="d04a6-155">FQDN name that SBC must present in the Contact header when sending calls to users</span></span>|
|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="d04a6-156">Customers.adatum.Biz</span><span class="sxs-lookup"><span data-stu-id="d04a6-156">customers.adatum.biz</span></span>|    <span data-ttu-id="d04a6-157">Base</span><span class="sxs-lookup"><span data-stu-id="d04a6-157">Base</span></span>     |     <span data-ttu-id="d04a6-158">В поставщика для клиентов</span><span class="sxs-lookup"><span data-stu-id="d04a6-158">In carrier tenant</span></span>  |    <span data-ttu-id="d04a6-159">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="d04a6-159">\*.customers.adatum.biz</span></span>  |   <span data-ttu-id="d04a6-160">adatum.Biz</span><span class="sxs-lookup"><span data-stu-id="d04a6-160">adatum.biz</span></span>      |<span data-ttu-id="d04a6-161">НД, это клиент службы, пользователи не</span><span class="sxs-lookup"><span data-stu-id="d04a6-161">NA, this is a service tenant, no users</span></span> |
|<span data-ttu-id="d04a6-162">sbc1.Customers.adatum.Biz</span><span class="sxs-lookup"><span data-stu-id="d04a6-162">sbc1.customers.adatum.biz</span></span>|    <span data-ttu-id="d04a6-163">Дочерний домен</span><span class="sxs-lookup"><span data-stu-id="d04a6-163">Subdomain</span></span>  |    <span data-ttu-id="d04a6-164">В клиентов клиента</span><span class="sxs-lookup"><span data-stu-id="d04a6-164">In a customer tenant</span></span>  |    <span data-ttu-id="d04a6-165">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="d04a6-165">\*.customers.adatum.biz</span></span>  | <span data-ttu-id="d04a6-166">woodgrovebank.US</span><span class="sxs-lookup"><span data-stu-id="d04a6-166">woodgrovebank.us</span></span>  |  <span data-ttu-id="d04a6-167">sbc1.Customers.adatum.Biz</span><span class="sxs-lookup"><span data-stu-id="d04a6-167">sbc1.customers.adatum.biz</span></span>|
|<span data-ttu-id="d04a6-168">sbc2.Customers.adatum.Biz</span><span class="sxs-lookup"><span data-stu-id="d04a6-168">sbc2.customers.adatum.biz</span></span>  |   <span data-ttu-id="d04a6-169">Дочерний домен</span><span class="sxs-lookup"><span data-stu-id="d04a6-169">Subdomain</span></span> | <span data-ttu-id="d04a6-170">В клиентов клиента</span><span class="sxs-lookup"><span data-stu-id="d04a6-170">In a customer tenant</span></span>   |   <span data-ttu-id="d04a6-171">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="d04a6-171">\*.customers.adatum.biz</span></span>   |<span data-ttu-id="d04a6-172">Contoso.com</span><span class="sxs-lookup"><span data-stu-id="d04a6-172">contoso.com</span></span>   |<span data-ttu-id="d04a6-173">sbc2.Customers.adatum.Biz</span><span class="sxs-lookup"><span data-stu-id="d04a6-173">sbc2.customers.adatum.biz</span></span> |
|<span data-ttu-id="d04a6-174">sbc3.Customers.adatum.Biz</span><span class="sxs-lookup"><span data-stu-id="d04a6-174">sbc3.customers.adatum.biz</span></span> |   <span data-ttu-id="d04a6-175">Дочерний домен</span><span class="sxs-lookup"><span data-stu-id="d04a6-175">Subdomain</span></span> | <span data-ttu-id="d04a6-176">В клиентов клиента</span><span class="sxs-lookup"><span data-stu-id="d04a6-176">In a customer tenant</span></span> |   <span data-ttu-id="d04a6-177">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="d04a6-177">\*.customers.adatum.biz</span></span>  |  <span data-ttu-id="d04a6-178">AdventureWorks.com</span><span class="sxs-lookup"><span data-stu-id="d04a6-178">adventureworks.com</span></span> | <span data-ttu-id="d04a6-179">sbc3.Customers.adatum.Biz</span><span class="sxs-lookup"><span data-stu-id="d04a6-179">sbc3.customers.adatum.biz</span></span> |
||         |         |         |         |         |

<span data-ttu-id="d04a6-180">Чтобы настроить базы и дочерние домены, выполните описанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d04a6-180">To configure the base and subdomains, please follow the steps described below.</span></span> <span data-ttu-id="d04a6-181">В примере мы настроим базового доменное имя (customers.adatum.biz) и дочерний домен для одного клиента (sbc1.customers.adatum.biz в банка Woodgrove клиентов).</span><span class="sxs-lookup"><span data-stu-id="d04a6-181">In the example, we will configure a base domain name (customers.adatum.biz) and a subdomain for one customer (sbc1.customers.adatum.biz in Woodgrove Bank tenant).</span></span>

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a><span data-ttu-id="d04a6-182">Регистрация имени базового домена в клиентов поставщика</span><span class="sxs-lookup"><span data-stu-id="d04a6-182">Register a base domain name in the carrier tenant</span></span>

<span data-ttu-id="d04a6-183">**Эти действия выполняются в поставщика для клиентов.**</span><span class="sxs-lookup"><span data-stu-id="d04a6-183">**These actions are performed in the carrier tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a><span data-ttu-id="d04a6-184">Убедитесь, что соответствующие права в клиентов поставщика</span><span class="sxs-lookup"><span data-stu-id="d04a6-184">Ensure that you have appropriate rights in the carrier tenant</span></span>

<span data-ttu-id="d04a6-185">Новые домены можно добавить только в том случае, если вы вошли Центр администрирования Office 365, как глобальный администратор.</span><span class="sxs-lookup"><span data-stu-id="d04a6-185">You can only add new domains if you signed in to the Office 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="d04a6-186">Для проверки роли, у вас есть, выполните вход в центр администрирования Microsoft 365 (https://portal.office.com), последовательно выберите пункты **Пользователи** > **Активных пользователей**, а затем убедитесь, что у вас есть роль глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="d04a6-186">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="d04a6-187">Дополнительные сведения о роли администраторов, а также необходимо назначить роль в Office 365 можно [роли администраторов об Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span><span class="sxs-lookup"><span data-stu-id="d04a6-187">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a><span data-ttu-id="d04a6-188">Добавление базового домена к клиенту и для проверки</span><span class="sxs-lookup"><span data-stu-id="d04a6-188">Add a base domain to the tenant and verify it</span></span>

1.  <span data-ttu-id="d04a6-189">В центре администрирования Microsoft 365 перейдите в окно **Установка** > **домены** > **Добавить домен**.</span><span class="sxs-lookup"><span data-stu-id="d04a6-189">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2.  <span data-ttu-id="d04a6-190">В поле **Введите имя домена, которое вы владеете** введите полное доменное имя базового домена.</span><span class="sxs-lookup"><span data-stu-id="d04a6-190">In the **Enter a domain you own** box, type the FQDN of the base domain.</span></span> <span data-ttu-id="d04a6-191">В следующем примере базового домена — *customers.adatum.biz*.</span><span class="sxs-lookup"><span data-stu-id="d04a6-191">In the following example, the base domain is *customers.adatum.biz*.</span></span>

    ![Добавление базового домена](media/direct-routing-2-sbc-add-domain.png)

3. <span data-ttu-id="d04a6-193">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d04a6-193">Click **Next**.</span></span>
4. <span data-ttu-id="d04a6-194">В примере клиента уже adatum.biz подтвержденным доменное имя.</span><span class="sxs-lookup"><span data-stu-id="d04a6-194">In the example, the tenant already has adatum.biz as a verified domain name.</span></span> <span data-ttu-id="d04a6-195">Мастер не запрашивает дополнительную проверку из-за customers.adatum.biz дочерний домен для уже зарегистрированное имя.</span><span class="sxs-lookup"><span data-stu-id="d04a6-195">The wizard will not ask for additional verification because customers.adatum.biz is a subdomain for the already registered name.</span></span> <span data-ttu-id="d04a6-196">Тем не менее если добавить полное доменное имя, которое не было проверено перед необходимо пройти через процесс проверки.</span><span class="sxs-lookup"><span data-stu-id="d04a6-196">However, if you add an FQDN that has not been verified before, you will need to go through the process of verification.</span></span> <span data-ttu-id="d04a6-197">Процесс проверки, [описанные ниже](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span><span class="sxs-lookup"><span data-stu-id="d04a6-197">The process of verification is [described below](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span></span>

    ![Подтверждение verfied доменного имени](media/direct-routing-3-sbc-verify-domain.png)

5.  <span data-ttu-id="d04a6-199">Нажмите кнопку **Далее**на странице " **Параметры DNS обновление** " выберите **я добавите DNS-записи самостоятельно** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d04a6-199">Click **Next**, and on the **Update DNS Settings** page, select **I’ll add the DNS records myself** and click **Next**.</span></span>
6.  <span data-ttu-id="d04a6-200">На следующей странице, удалите все значения (Если вы хотите использовать имя домена для Exchange, SharePoint или команды/Скайп для бизнеса), нажмите кнопку **Далее**и затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d04a6-200">On the next page, clear all values (unless you want to use the domain name for Exchange, SharePoint, or Teams/Skype for Business), click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="d04a6-201">Убедитесь в том, что новый домен находится в состоянии завершения программы установки.</span><span class="sxs-lookup"><span data-stu-id="d04a6-201">Make sure your new domain is in the Setup complete status.</span></span>

    ![Домены, отображение состояния установки завершена](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a><span data-ttu-id="d04a6-203">Активация имя домена</span><span class="sxs-lookup"><span data-stu-id="d04a6-203">Activate the domain name</span></span>

<span data-ttu-id="d04a6-204">После регистрации имени домена, необходимо включить его, добавив по крайней мере один пользователь и назначьте SIP-адрес с помощью полного доменного ИМЕНИ части соответствия создан базовый домен SIP-адрес.</span><span class="sxs-lookup"><span data-stu-id="d04a6-204">After you have registered a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created base domain.</span></span>

<span data-ttu-id="d04a6-205">*Ознакомьтесь с [Получение справки по работе с Office 365 домены](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) Дополнительные сведения о добавлении пользователей в клиентов Office 365.*</span><span class="sxs-lookup"><span data-stu-id="d04a6-205">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="d04a6-206">Например: test@customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="d04a6-206">For example: test@customers.adatum.biz</span></span>

![Страница активации базового домена](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a><span data-ttu-id="d04a6-208">Регистрация имени дочернего домена в клиентов клиента</span><span class="sxs-lookup"><span data-stu-id="d04a6-208">Register a subdomain name in a customer tenant</span></span>

<span data-ttu-id="d04a6-209">Необходимо будет создать поддомен уникальное имя для каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="d04a6-209">You will need to create a unique subdomain name for every customer.</span></span> <span data-ttu-id="d04a6-210">В этом примере мы создадим sbc1.customers.adatum.biz дочерний домен в клиент с woodgrovebank.us имя домена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d04a6-210">In this example, we will create a subdomain sbc1.customers.adatum.biz in a tenant with the default domain name woodgrovebank.us.</span></span>

<span data-ttu-id="d04a6-211">**Все действия, ниже, в клиента для клиентов.**</span><span class="sxs-lookup"><span data-stu-id="d04a6-211">**All actions below are in the customer tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a><span data-ttu-id="d04a6-212">Убедитесь, что соответствующие права в клиента для клиентов</span><span class="sxs-lookup"><span data-stu-id="d04a6-212">Ensure that you have appropriate rights in the customer tenant</span></span>

<span data-ttu-id="d04a6-213">Новые домены можно добавить только в том случае, если вы вошли Центр администрирования Office 365, как глобальный администратор.</span><span class="sxs-lookup"><span data-stu-id="d04a6-213">You can only add new domains if you signed in to the Office 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="d04a6-214">Для проверки роли, у вас есть, выполните вход в центр администрирования Microsoft 365 (https://portal.office.com), последовательно выберите пункты **Пользователи** > **Активных пользователей**, а затем убедитесь, что у вас есть роль глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="d04a6-214">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="d04a6-215">Дополнительные сведения о роли администраторов, а также необходимо назначить роль в Office 365 можно [роли администраторов об Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span><span class="sxs-lookup"><span data-stu-id="d04a6-215">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a><span data-ttu-id="d04a6-216">Добавить поддомен в клиент клиентов и для проверки</span><span class="sxs-lookup"><span data-stu-id="d04a6-216">Add a subdomain to the customer tenant and verify it</span></span>
1. <span data-ttu-id="d04a6-217">В центре администрирования Microsoft 365 перейдите в окно **Установка** > **домены** > **Добавить домен**.</span><span class="sxs-lookup"><span data-stu-id="d04a6-217">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="d04a6-218">В поле **Введите имя домена, которое вы владеете** введите полное доменное имя дочерний домен для клиента.</span><span class="sxs-lookup"><span data-stu-id="d04a6-218">In the **Enter a domain you own** box, type the FQDN of the subdomain for this tenant.</span></span> <span data-ttu-id="d04a6-219">В приведенном ниже примере дочерний домен не sbc1.customers.adatum.biz.</span><span class="sxs-lookup"><span data-stu-id="d04a6-219">In the example below, the subdomain is sbc1.customers.adatum.biz.</span></span>

    ![Добавление дочернего домена клиента](media/direct-routing-5-sbc-add-customer-domain.png)

3. <span data-ttu-id="d04a6-221">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d04a6-221">Click **Next**.</span></span>
4. <span data-ttu-id="d04a6-222">Полное доменное имя, никогда не зарегистрирован в клиента.</span><span class="sxs-lookup"><span data-stu-id="d04a6-222">The FQDN has never been registered in the tenant.</span></span> <span data-ttu-id="d04a6-223">На следующем этапе необходимо проверить домен.</span><span class="sxs-lookup"><span data-stu-id="d04a6-223">In the next step, you will need to verify the domain.</span></span> <span data-ttu-id="d04a6-224">Выберите **вместо добавления записи TXT**.</span><span class="sxs-lookup"><span data-stu-id="d04a6-224">Select **Add a TXT record instead**.</span></span> 

    ![Параметры на странице Проверка домена](media/direct-routing-6-sbc-verify-customer-domain.png)

5. <span data-ttu-id="d04a6-226">Нажмите кнопку **Далее**и обратите внимание на значение записи TXT, созданные для проверки имени домена.</span><span class="sxs-lookup"><span data-stu-id="d04a6-226">Click **Next**, and note the TXT value generated to verify the domain name.</span></span>

    ![Текст записей на странице Проверка домена](media/direct-routing-7-sbc-verify-domain-txt.png)

6. <span data-ttu-id="d04a6-228">Создайте запись TXT со значением из предыдущего шага в транспортной поставщика услуг размещения DNS.</span><span class="sxs-lookup"><span data-stu-id="d04a6-228">Create the TXT record with the value from the previous step in carrier’s DNS hosting provider.</span></span>

    ![Создание записи TXT в транспортной поставщика услуг размещения DNS](media/direct-routing-8-sbc-txt-record.png)

    <span data-ttu-id="d04a6-230">Для получения дополнительных сведений обратитесь к [статье Создание записей DNS на любой поставщика услуг размещения DNS для Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span><span class="sxs-lookup"><span data-stu-id="d04a6-230">For more information, refer to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span></span>

7. <span data-ttu-id="d04a6-231">Вернитесь в центр администрирования Microsoft 365 клиента и нажмите кнопку **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="d04a6-231">Go back to the customer's Microsoft 365 admin center and click **Verify**.</span></span> 
8. <span data-ttu-id="d04a6-232">На следующей странице выберите **я добавите DNS-записи самостоятельно** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d04a6-232">On the next page, select **I’ll add the DNS records myself** and click **Next**.</span></span>

    ![Параметры на странице параметров обновления DNS](media/direct-routing-9-sbc-update-dns.png)

9. <span data-ttu-id="d04a6-234">На странице **Выбор интерактивных служб** снимите все флажки и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d04a6-234">On the **Choose your online services** page, clear all options and click **Next**.</span></span>

    ![Выбор страницы Интернет-служб](media/direct-routing-10-sbc-choose-services.png)

10. <span data-ttu-id="d04a6-236">На странице " **параметры DNS обновления** " нажмите кнопку **Готово** .</span><span class="sxs-lookup"><span data-stu-id="d04a6-236">Click **Finish** on the **Update DNS settings** page.</span></span>

    ![Страница параметров обновления DNS](media/direct-routing-11-sbc-update-dns-finish.png)

11. <span data-ttu-id="d04a6-238">Убедитесь, что состояние **выполнения программы установки**.</span><span class="sxs-lookup"><span data-stu-id="d04a6-238">Ensure that the status is **Setup complete**.</span></span> 
    
    ![Страница состояния установки завершена](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a><span data-ttu-id="d04a6-240">Активация имя дочернего домена</span><span class="sxs-lookup"><span data-stu-id="d04a6-240">Activate the subdomain name</span></span>

<span data-ttu-id="d04a6-241">После регистрации имени домена, необходимо включить его, добавив по крайней мере один пользователь и назначьте SIP-адрес с помощью полного доменного ИМЕНИ части SIP-адрес соответствия созданного дочернего домена в клиента для клиентов.</span><span class="sxs-lookup"><span data-stu-id="d04a6-241">After you register a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created subdomain in the customer tenant.</span></span>

<span data-ttu-id="d04a6-242">*Ознакомьтесь с [Получение справки по работе с Office 365 домены](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) Дополнительные сведения о добавлении пользователей в клиентов Office 365.*</span><span class="sxs-lookup"><span data-stu-id="d04a6-242">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="d04a6-243">Например: test@sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="d04a6-243">For example: test@sbc1.customers.adatum.biz</span></span>

![Активация страницы дочернего домена](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a><span data-ttu-id="d04a6-245">Создание линии связи и подготовки пользователей</span><span class="sxs-lookup"><span data-stu-id="d04a6-245">Create a trunk and provision users</span></span>

> [!NOTE]
> <span data-ttu-id="d04a6-246">На основании отзывов, полученных в программе технического внедрения, корпорация Майкрософт может изменять процесс создания магистралей в клиенты клиента для упрощения процесса.</span><span class="sxs-lookup"><span data-stu-id="d04a6-246">Based on feedback we received in the Technical Adoption Program, Microsoft might change the process of creating trunks in the customer tenants to simplify the process.</span></span> <span data-ttu-id="d04a6-247">Просмотрите документацию обновлений на этой странице и следуйте блоги Технические сообщества Майкрософт для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="d04a6-247">Please watch the documentation updates on this page and follow the Microsoft Technical Community blogs for further information.</span></span> 

<span data-ttu-id="d04a6-248">Создайте магистрали в домене клиента, с помощью команды New-CSonlinePSTNGateway.</span><span class="sxs-lookup"><span data-stu-id="d04a6-248">Create a trunk in the customer domain using the New-CSonlinePSTNGateway command.</span></span> <span data-ttu-id="d04a6-249">Линии связи, полное доменное имя **должно** соответствовать дочерний домен, созданных для клиента.</span><span class="sxs-lookup"><span data-stu-id="d04a6-249">The trunk FQDN **MUST** match the subdomain created for the customer.</span></span>

<span data-ttu-id="d04a6-250">Например:</span><span class="sxs-lookup"><span data-stu-id="d04a6-250">For example:</span></span>

<span data-ttu-id="d04a6-251">*Новые CSOnlinePSTNGateway – полное доменное имя sbc1.customers.adatum.biz - SipSignallingPort 5068*</span><span class="sxs-lookup"><span data-stu-id="d04a6-251">*New-CSOnlinePSTNGateway – FQDN sbc1.customers.adatum.biz -SipSignallingPort 5068*</span></span>

<span data-ttu-id="d04a6-252">Подготовка пользователей с телефонных номеров и настройка маршрутизации голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="d04a6-252">Provision users with the phone numbers and configure voice routing.</span></span>

<span data-ttu-id="d04a6-253">Дополнительные сведения о New-CSOnlinePSTNGateway подготовки пользователей и настройка маршрутизации голосовой связи, обратитесь к [Настройка прямой маршрутизации](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="d04a6-253">For more information on the New-CSOnlinePSTNGateway, provisioning users, and configuring voice routing, please refer to [Configure Direct Routing](direct-routing-configure.md).</span></span>


<span data-ttu-id="d04a6-254">Обратитесь к [SBC поставщика инструкции](#deploy-and-configure-the-sbc) по настройке отправки полное ДОМЕННОЕ имя поддоменов в заголовке контакта.</span><span class="sxs-lookup"><span data-stu-id="d04a6-254">Please refer to the [SBC vendor instructions](#deploy-and-configure-the-sbc) on configuring sending the FQDN name of subdomains in the Contact header.</span></span>

