---
title: Обзор приложения для пациентов
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Узнайте о том, как интегрировать электронные записи в здравоохранение в приложение Microsoft Teams пациентов с помощью API-интерфейсов FHIR.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f981b2fc68aa52f8ea5a48fab18977197ac813c8
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098427"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="8ea3b-103">Интеграция электронных историй болезни в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8ea3b-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="8ea3b-104">Эта статья предназначена для общего СПЕЦИАЛИСТа, заинтересованного в использовании API FHIR в верхней части системы медицинских данных для подключения к Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-104">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="8ea3b-105">Это позволит соблюдать сценарии координирования, соответствующие потребностям организации здравоохранения.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-105">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="8ea3b-106">Связанные статьи. документ: спецификации интерфейса FHIR для приложения Microsoft Teams пациентов и следующие разделы содержат сведения о том, что необходимо для настройки сервера FHIR и подключения к приложению пациентов в среде разработки или в клиенте.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-106">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="8ea3b-107">Вам также необходимо ознакомиться с документацией по выбранному серверу FHIR, который должен быть одним из поддерживаемых вариантов:</span><span class="sxs-lookup"><span data-stu-id="8ea3b-107">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>
- <span data-ttu-id="8ea3b-108">Datica (в рамках своего [CMIного](https://datica.com/compliant-managed-integration/) предложения)</span><span class="sxs-lookup"><span data-stu-id="8ea3b-108">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="8ea3b-109">Cloverleaf информационного моста (через [мост FHIR](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span><span class="sxs-lookup"><span data-stu-id="8ea3b-109">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="8ea3b-110">Redox (с помощью [сервера R ^ FHIR](https://www.redoxengine.com/fhir/))</span><span class="sxs-lookup"><span data-stu-id="8ea3b-110">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="8ea3b-111">Dapasoft (до [Corolar на FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span><span class="sxs-lookup"><span data-stu-id="8ea3b-111">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="8ea3b-112">Этот процесс не включает шаги, которые используют центр администрирования Microsoft Teams или командлеты PowerShell для включения функций.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-112">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="8ea3b-113">Конфигурация полностью выполняется на стороне сервера или службы FHIR и в клиенте приложения пациентов.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-113">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="8ea3b-114">Ниже показано, как архитектура приложения пациентов.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-114">Illustrated below is the architecture of the Patients app:</span></span>

![Схема архитектуры приложения пациентов](../../media/patients-app-architecture.png)

<span data-ttu-id="8ea3b-116">В следующих разделах описаны требования уровня доступа к данным "FHIR" для приложения пациентов, которому должны соответствовать FHIR сервер (или EHR включения FHIR API) для интеграции с приложением пациентов, в том числе описанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-116">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="8ea3b-117">Ожидаемые решения для проверки подлинности пользователя</span><span class="sxs-lookup"><span data-stu-id="8ea3b-117">Expectations around user authentication</span></span>
- <span data-ttu-id="8ea3b-118">Функциональные и технические требования к интерфейсу интеграции</span><span class="sxs-lookup"><span data-stu-id="8ea3b-118">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="8ea3b-119">Ожидание в отношении производительности и надежности</span><span class="sxs-lookup"><span data-stu-id="8ea3b-119">Expectations around performance and reliability</span></span>
- <span data-ttu-id="8ea3b-120">Ожидания для FHIRных ресурсов, которые должны поддерживаться в приложении пациентов</span><span class="sxs-lookup"><span data-stu-id="8ea3b-120">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="8ea3b-121">Процесс интеграции и ожидаемая модель задействования</span><span class="sxs-lookup"><span data-stu-id="8ea3b-121">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="8ea3b-122">Как начать работу с FHIR и некоторые распространенные проблемы, с которыми сталкиваются с приложением пациентов</span><span class="sxs-lookup"><span data-stu-id="8ea3b-122">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="8ea3b-123">Будущие требования к следующей итерации приложения пациентов</span><span class="sxs-lookup"><span data-stu-id="8ea3b-123">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="8ea3b-124">В следующих разделах слово "партнер" или "партнер по взаимодействию" используется для ссылки на независимую организацию, которая обеспечивает интеграцию с EHR системами для приложения пациентов через FHIR и реализует FHIR сервер для соответствия указанным спецификациям.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-124">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="8ea3b-125">Функциональные и технические требования</span><span class="sxs-lookup"><span data-stu-id="8ea3b-125">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="8ea3b-126">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="8ea3b-126">Authentication</span></span>  

<span data-ttu-id="8ea3b-127">Авторизация на уровне приложений без *поддержки авторизации на уровне пользователей* — это наиболее распространенный способ выполнения преобразования данных и предоставления доступа к данным EHR через FHIR, даже если система EHR может реализовать авторизацию на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-127">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="8ea3b-128">Служба взаимодействия (Partner) получает доступ к данным EHR с повышенными привилегиями, и когда они предоставляют те же данные, что и соответствующие ресурсы FHIR, то контекст авторизации не передается потребителю службы взаимодействия (приложение пациентов), интеграция со службой взаимодействия или платформой.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-128">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="8ea3b-129">Приложение пациентов не сможет применять авторизацию на уровне пользователей, но поддерживает проверку подлинности приложения между приложением пациентов и службой партнера по взаимодействию.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-129">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner's service.</span></span>

<span data-ttu-id="8ea3b-130">Модель проверки подлинности приложения для приложения описана ниже.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-130">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="8ea3b-131">Проверка подлинности службы для проверки должна выполняться с помощью [потока учетных данных клиента](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)OAuth 2,0.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-131">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="8ea3b-132">Служба-партнер должна предоставить следующее:</span><span class="sxs-lookup"><span data-stu-id="8ea3b-132">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="8ea3b-133">Служба Partner позволяет приложению пациентов создать учетную запись с партнером, которая позволяет приложению пациентов создавать и владеть client_id и client_secret, управляемым с помощью портала регистрации проверки подлинности на сервере аутентификации партнера.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-133">The Partner service enables the Patients app to create an account with the Partner, which enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner's Authentication server.</span></span>
2. <span data-ttu-id="8ea3b-134">Служба-партнер владеет системой проверки подлинности и авторизации, которая принимает и проверяет (проверяет подлинность) предоставленные учетные данные клиента и возвращает маркер доступа с указанием клиента в области действия, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-134">The Partner service owns the Authentication/Authorization system, which accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>
3. <span data-ttu-id="8ea3b-135">В целях обеспечения безопасности, а также в случае нарушения секретности приложение пациентов может повторно создать секретный код и сделать недействительным или удалить старый секрет (пример такого же можно найти на портале Azure — регистрация приложений AAD).</span><span class="sxs-lookup"><span data-stu-id="8ea3b-135">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (example of the same is available in Azure Portal - AAD App Registration).</span></span>
4. <span data-ttu-id="8ea3b-136">Для конечной точки метаданных, в которой размещена Инструкция по обеспечению соответствия, необходимо отменить проверку подлинности, поэтому она должна быть доступна без маркера проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-136">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>
5. <span data-ttu-id="8ea3b-137">Служба Partner предоставляет конечной точке маркера для приложения пациентов запрос токена доступа с помощью потока учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-137">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="8ea3b-138">URL-адрес маркера, указанный на сервере авторизации, должен быть частью инструкции FHIR (возможности), полученной из метаданных на сервере FHIR, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8ea3b-138">The token url as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

* * *
    <span data-ttu-id="8ea3b-139">{"resourceType": "CapabilityStatement";</span><span class="sxs-lookup"><span data-stu-id="8ea3b-139">{ "resourceType": "CapabilityStatement", .</span></span>
        <span data-ttu-id="8ea3b-140">.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-140">.</span></span>
        <span data-ttu-id="8ea3b-141">.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-141">.</span></span>
        <span data-ttu-id="8ea3b-142">"оставшаяся: [{" Mode ":" сервер "," безопасность ": {" расширение ": [{" расширение ": [{" URL ":" token "," valueUri ":" https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token "}, {" URL-адрес ":" Авторизация "," valueUri ":" "}]," https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize URL-адрес ": http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris [{" System ":" https://hl7.org/fhir/ValueSet/restful-security-service "," код ":" OAuth "}]}]},.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-142">"rest": [ { "mode": "server", "security": { "extension": [ { "extension": [ { "url": "token", "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token" }, { "url": "authorize", "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize" } ], "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris" } ], "service": [ { "coding": [ { "system": "https://hl7.org/fhir/ValueSet/restful-security-service", "code": "OAuth" } ] } ] }, .</span></span>
                <span data-ttu-id="8ea3b-143">.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-143">.</span></span>
                <span data-ttu-id="8ea3b-144">.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-144">.</span></span>
            <span data-ttu-id="8ea3b-145">} ] }</span><span class="sxs-lookup"><span data-stu-id="8ea3b-145">} ] }</span></span>

* * *

<span data-ttu-id="8ea3b-146">Запрос маркера доступа состоит из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="8ea3b-146">A request for an access token consists of the following parameters:</span></span>

* * *

    <span data-ttu-id="8ea3b-147">Публикация узла HTTP/1.1/Token: authorization-server.com</span><span class="sxs-lookup"><span data-stu-id="8ea3b-147">POST /token HTTP/1.1 Host: authorization-server.com</span></span>

    <span data-ttu-id="8ea3b-148">Grant-Type = client_credentials &client_id = XXXXXXXXXX &client_secret = XXXXXXXXXX</span><span class="sxs-lookup"><span data-stu-id="8ea3b-148">grant-type=client_credentials &client_id=xxxxxxxxxx &client_secret=xxxxxxxxxx</span></span>

* * *

<span data-ttu-id="8ea3b-149">Служба Partner предоставляет client_id и client_secret для приложения пациентов, управляемого через портал регистрации проверки подлинности на стороне партнера.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-149">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner's side.</span></span> <span data-ttu-id="8ea3b-150">Служба Partner предоставляет конечной точке запрос на доступ к маркеру доступа с помощью потока учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-150">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="8ea3b-151">Успешный ответ должен включать параметры token_type, access_token и expires_in.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-151">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="8ea3b-152">Routing: сопоставление клиента AAD с конечной точкой поставщика</span><span class="sxs-lookup"><span data-stu-id="8ea3b-152">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="8ea3b-153">Приложение пациентов подключается к службе-партнеру через одну конечную точку.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-153">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="8ea3b-154">Служба-партнер владеет и поддерживает механизм сопоставления каждого клиента Майкрософт (ИД клиента AAD) соответствующему поставщику здравоохранения (сервер FHIR), с которым работает служба Partner.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-154">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="8ea3b-155">Сопоставление клиента AAD с конечной точкой поставщика использует идентификатор клиента AAD (GUID).</span><span class="sxs-lookup"><span data-stu-id="8ea3b-155">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="8ea3b-156">Приложение пациентов передает идентификатор клиента в области, запросив маркер доступа для каждого запроса.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-156">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="8ea3b-157">Служба Partner хранит сопоставление идентификатора клиента и конечной точки поставщика и перенаправляет запросы в конечную точку поставщика на основе идентификатора клиента.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-157">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="8ea3b-158">Для этого партнер поддерживает конфигурацию на своем окончании (вручную или через портал в рамках встроенной Организации поставщиков на платформу взаимодействия).</span><span class="sxs-lookup"><span data-stu-id="8ea3b-158">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="8ea3b-159">Рабочий процесс проверки подлинности и маршрутизации показан ниже.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-159">The Authentication and Routing workflow is shown below:</span></span>

![Схема рабочего процесса маршрутизации и проверки подлинности](../../media/Patient-app-6.png)

1. <span data-ttu-id="8ea3b-161">Запрос маркера доступа к приложению путем отправки:</span><span class="sxs-lookup"><span data-stu-id="8ea3b-161">Request for app access token by sending:</span></span>
 
        {   grant_type: client_credentials,
            client_id: xxxxxx, 
            client_secret: xxxxxx,
            scope: {Provider Identifier, Ex: tenant ID}
        }

2. <span data-ttu-id="8ea3b-162">Ответьте на маркер приложения:</span><span class="sxs-lookup"><span data-stu-id="8ea3b-162">Reply with an app token:</span></span>

        {  access_token: {JWT, with scope: tenant ID},
           expires_in: 156678,
           token_type: "Bearer",
        }

3. <span data-ttu-id="8ea3b-163">Запросите защищенные данные с помощью маркера доступа.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-163">Request protected data with Access token.</span></span>
4. <span data-ttu-id="8ea3b-164">Сообщение о проверке подлинности: выберите соответствующий сервер FHIR для маршрутизации из идентификатора клиента в области</span><span class="sxs-lookup"><span data-stu-id="8ea3b-164">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope</span></span>
5. <span data-ttu-id="8ea3b-165">Отправляет данные, защищенные приложением, от авторизованного сервера FHIR после проверки подлинности с помощью маркера приложения.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-165">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="8ea3b-166">Приклад</span><span class="sxs-lookup"><span data-stu-id="8ea3b-166">Interfaces</span></span>

<span data-ttu-id="8ea3b-167">Специальные вызовы и поля, используемые приложением пациентов, описаны в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-167">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="8ea3b-168">Выберите интерфейс, применимый к интерфейсам API FHIR и FHIR сервера.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-168">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="8ea3b-169">Характеристики интерфейса DSTU2</span><span class="sxs-lookup"><span data-stu-id="8ea3b-169">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="8ea3b-170">Характеристики интерфейса STU3</span><span class="sxs-lookup"><span data-stu-id="8ea3b-170">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="8ea3b-171">Производительность и надежность</span><span class="sxs-lookup"><span data-stu-id="8ea3b-171">Performance and Reliability</span></span>

<span data-ttu-id="8ea3b-172">Несмотря на то, что приложение пациентов в закрытом предварительном просмотре, нет гарантии на производительность "на конец".</span><span class="sxs-lookup"><span data-stu-id="8ea3b-172">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="8ea3b-173">Факторы, влияющие на производительность, включают относительную задержку всех переходов, участвующих в рабочем процессе, начиная с EHR в среде системы работоспособности и до партнера по взаимодействию, включая сервер FHIR и в приложение Office 365 для экосистемы и пациентов.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-173">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![Иллюстрация производительности партнеров по взаимодействию](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="8ea3b-175">Начало работы с FHIR</span><span class="sxs-lookup"><span data-stu-id="8ea3b-175">Get started with FHIR</span></span>  

<span data-ttu-id="8ea3b-176">Если вы новичок в FHIR и вам нужно легко получить доступ к серверу FHIR, который можно использовать для интерфейса интеграции Microsoft Teams EHR, корпорация Майкрософт предоставляет доступ к серверу FHIR с открытым исходным кодом для всех разработчиков.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-176">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="8ea3b-177">Ознакомьтесь со статьей " [что такое сервер FHIR для Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) ", чтобы узнать больше о сервере Open Source FHIR, доступном в Microsoft, и его развертывании для организаций.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-177">Please see the [What is FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="8ea3b-178">Вы также можете использовать среду HSPC Open песочницы EHR, чтобы создать EHR, который также поддерживает открытый сервер FHIR и использовать его для воспроизведения с помощью приложения пациентов.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-178">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="8ea3b-179">Мы рекомендуем ознакомиться с [документацией по программной среде HSPC](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span><span class="sxs-lookup"><span data-stu-id="8ea3b-179">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="8ea3b-180">Среда выполнения не только предоставляет простой, ориентированный на пользовательский интерфейс и удобный способ создания, добавления и редактирования пациентов, он также предоставляет несколько образцов для начала работы.</span><span class="sxs-lookup"><span data-stu-id="8ea3b-180">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span> 