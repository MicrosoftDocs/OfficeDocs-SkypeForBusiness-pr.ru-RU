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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 594375959a8cd7cbbfc21c6b9d5ceb6c0f8a8dac
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803547"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="e5b6a-103">Интеграция электронных историй болезни в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e5b6a-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="e5b6a-104">Действительно 30 октября 2020 г. приложение пациентов было прекращено и заменено [приложением "списки](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) " в Teams.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="e5b6a-105">Данные приложения пациентов хранятся в почтовом ящике группы Office 365, которая является резервной командой.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="e5b6a-106">Все данные, связанные с приложением пациентов, сохраняются в этой группе, но их больше нельзя будет получить с помощью пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="e5b6a-107">Пользователи могут повторно создавать списки с помощью приложения " [списки](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)".</span><span class="sxs-lookup"><span data-stu-id="e5b6a-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="e5b6a-108">Благодаря спискам, благодаря вашим командам в организации здравоохранения вы сможете создавать списки пациент для сценариев, начиная с округляющих и interdisciplinaryных собраний групп и заканчивая общим мониторингом пациента.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="e5b6a-109">Чтобы приступить к работе, изучите шаблон пациентов в списках.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="e5b6a-110">Дополнительные сведения об управлении приложением Lists в Организации можно найти в разделе [Управление приложением "списки"](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="e5b6a-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="e5b6a-111">Эта статья предназначена для общего СПЕЦИАЛИСТа, заинтересованного в использовании API FHIR в верхней части системы медицинских данных для подключения к Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-111">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="e5b6a-112">Это позволит соблюдать сценарии координирования, соответствующие потребностям организации здравоохранения.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-112">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="e5b6a-113">Связанные статьи. документ: спецификации интерфейса FHIR для приложения Microsoft Teams пациентов и следующие разделы содержат сведения о том, что необходимо для настройки сервера FHIR и подключения к приложению пациентов в среде разработки или в клиенте.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-113">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="e5b6a-114">Вам также необходимо ознакомиться с документацией по выбранному серверу FHIR, который должен быть одним из поддерживаемых вариантов:</span><span class="sxs-lookup"><span data-stu-id="e5b6a-114">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>

- <span data-ttu-id="e5b6a-115">Datica (в рамках своего [CMIного](https://datica.com/compliant-managed-integration/) предложения)</span><span class="sxs-lookup"><span data-stu-id="e5b6a-115">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="e5b6a-116">Cloverleaf информационного моста (через [мост FHIR](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span><span class="sxs-lookup"><span data-stu-id="e5b6a-116">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="e5b6a-117">Redox (с помощью [сервера R ^ FHIR](https://www.redoxengine.com/fhir/))</span><span class="sxs-lookup"><span data-stu-id="e5b6a-117">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="e5b6a-118">Dapasoft (до [Corolar на FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span><span class="sxs-lookup"><span data-stu-id="e5b6a-118">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="e5b6a-119">Этот процесс не включает шаги, которые используют центр администрирования Microsoft Teams или командлеты PowerShell для включения функций.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-119">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="e5b6a-120">Конфигурация полностью выполняется на стороне сервера или службы FHIR и в клиенте приложения пациентов.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-120">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="e5b6a-121">Ниже показано, как архитектура приложения пациентов.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-121">Illustrated below is the architecture of the Patients app:</span></span>

![Схема архитектуры приложения пациентов](../../media/patients-app-architecture.png)

<span data-ttu-id="e5b6a-123">В следующих разделах описаны требования уровня доступа к данным "FHIR" для приложения пациентов, которому должны соответствовать FHIR сервер (или EHR включения FHIR API) для интеграции с приложением пациентов, в том числе описанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-123">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="e5b6a-124">Ожидаемые решения для проверки подлинности пользователя</span><span class="sxs-lookup"><span data-stu-id="e5b6a-124">Expectations around user authentication</span></span>
- <span data-ttu-id="e5b6a-125">Функциональные и технические требования к интерфейсу интеграции</span><span class="sxs-lookup"><span data-stu-id="e5b6a-125">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="e5b6a-126">Ожидание в отношении производительности и надежности</span><span class="sxs-lookup"><span data-stu-id="e5b6a-126">Expectations around performance and reliability</span></span>
- <span data-ttu-id="e5b6a-127">Ожидания для FHIRных ресурсов, которые должны поддерживаться в приложении пациентов</span><span class="sxs-lookup"><span data-stu-id="e5b6a-127">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="e5b6a-128">Процесс интеграции и ожидаемая модель задействования</span><span class="sxs-lookup"><span data-stu-id="e5b6a-128">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="e5b6a-129">Как начать работу с FHIR и некоторые распространенные проблемы, с которыми сталкиваются с приложением пациентов</span><span class="sxs-lookup"><span data-stu-id="e5b6a-129">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="e5b6a-130">Будущие требования к следующей итерации приложения пациентов</span><span class="sxs-lookup"><span data-stu-id="e5b6a-130">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="e5b6a-131">В следующих разделах слово "партнер" или "партнер по взаимодействию" используется для ссылки на независимую организацию, которая обеспечивает интеграцию с EHR системами для приложения пациентов через FHIR и реализует FHIR сервер для соответствия указанным спецификациям.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-131">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="e5b6a-132">Функциональные и технические требования</span><span class="sxs-lookup"><span data-stu-id="e5b6a-132">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="e5b6a-133">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="e5b6a-133">Authentication</span></span>  

<span data-ttu-id="e5b6a-134">Авторизация на уровне приложений без *поддержки авторизации на уровне пользователей* — это наиболее распространенный способ выполнения преобразования данных и предоставления доступа к данным EHR через FHIR, даже если система EHR может реализовать авторизацию на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-134">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="e5b6a-135">Служба взаимодействия (Partner) получает доступ к данным EHR с повышенными привилегиями, и когда они предоставляют те же данные, что и соответствующие ресурсы FHIR, то контекст авторизации не передается потребителю службы взаимодействия (приложение пациентов), интеграция со службой взаимодействия или платформой.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-135">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="e5b6a-136">Приложение пациентов не сможет применять авторизацию на уровне пользователей, но поддерживает проверку подлинности приложения между приложением пациентов и службой партнера по взаимодействию.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-136">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner's service.</span></span>

<span data-ttu-id="e5b6a-137">Модель проверки подлинности приложения для приложения описана ниже.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-137">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="e5b6a-138">Проверка подлинности службы для проверки должна выполняться с помощью [потока учетных данных клиента](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)OAuth 2,0.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-138">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="e5b6a-139">Служба-партнер должна предоставить следующее:</span><span class="sxs-lookup"><span data-stu-id="e5b6a-139">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="e5b6a-140">Служба Partner позволяет приложению пациентов создать учетную запись с партнером, которая позволяет приложению пациентов создавать и владеть client_id и client_secret, управляемым с помощью портала регистрации проверки подлинности на сервере аутентификации партнера.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-140">The Partner service enables the Patients app to create an account with the Partner, which enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner's Authentication server.</span></span>

2. <span data-ttu-id="e5b6a-141">Служба-партнер владеет системой проверки подлинности и авторизации, которая принимает и проверяет (проверяет подлинность) предоставленные учетные данные клиента и возвращает маркер доступа с указанием клиента в области действия, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-141">The Partner service owns the Authentication/Authorization system, which accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>

3. <span data-ttu-id="e5b6a-142">В целях обеспечения безопасности, а также в случае нарушения секретности приложение пациентов может повторно создать секретный код и сделать недействительным или удалить старый секрет (пример такого же можно найти на портале Azure — регистрация приложений AAD).</span><span class="sxs-lookup"><span data-stu-id="e5b6a-142">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (example of the same is available in Azure Portal - AAD App Registration).</span></span>

4. <span data-ttu-id="e5b6a-143">Для конечной точки метаданных, в которой размещена Инструкция по обеспечению соответствия, необходимо отменить проверку подлинности, поэтому она должна быть доступна без маркера проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-143">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>

5. <span data-ttu-id="e5b6a-144">Служба Partner предоставляет конечной точке маркера для приложения пациентов запрос токена доступа с помощью потока учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-144">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="e5b6a-145">URL-адрес маркера, указанный на сервере авторизации, должен быть частью инструкции FHIR (возможности), полученной из метаданных на сервере FHIR, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e5b6a-145">The token URL as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

    ```
    {
        "resourceType": "CapabilityStatement",
        .
        .
        .
        "rest": [
            {
                "mode": "server",
                "security": {
                    "extension": [
                        {
                            "extension": [
                                {
                                    "url": "token",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token"
                                },
                                {
                                    "url": "authorize",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize"
                                }
                            ],
                            "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris"
                        }
                    ],
                    "service": [
                        {
                            "coding": [
                                {
                                    "system": "https://hl7.org/fhir/ValueSet/restful-security-service",
                                    "code": "OAuth"
                                }
                            ]
                        }
                    ]
                },
                .
                .
                .
            }
        ]
    }
    ```

<span data-ttu-id="e5b6a-146">Запрос маркера доступа состоит из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="e5b6a-146">A request for an access token consists of the following parameters:</span></span>

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

<span data-ttu-id="e5b6a-147">Служба Partner предоставляет client_id и client_secret для приложения пациентов, управляемого через портал регистрации проверки подлинности на стороне партнера.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-147">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner's side.</span></span> <span data-ttu-id="e5b6a-148">Служба Partner предоставляет конечной точке запрос на доступ к маркеру доступа с помощью потока учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-148">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="e5b6a-149">Успешный ответ должен включать параметры token_type, access_token и expires_in.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-149">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="e5b6a-150">Routing: сопоставление клиента AAD с конечной точкой поставщика</span><span class="sxs-lookup"><span data-stu-id="e5b6a-150">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="e5b6a-151">Приложение пациентов подключается к службе-партнеру через одну конечную точку.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-151">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="e5b6a-152">Служба-партнер владеет и поддерживает механизм сопоставления каждого клиента Майкрософт (ИД клиента AAD) соответствующему поставщику здравоохранения (сервер FHIR), с которым работает служба Partner.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-152">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="e5b6a-153">Сопоставление клиента AAD с конечной точкой поставщика использует идентификатор клиента AAD (GUID).</span><span class="sxs-lookup"><span data-stu-id="e5b6a-153">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="e5b6a-154">Приложение пациентов передает идентификатор клиента в области, запросив маркер доступа для каждого запроса.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-154">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="e5b6a-155">Служба Partner хранит сопоставление идентификатора клиента и конечной точки поставщика и перенаправляет запросы в конечную точку поставщика на основе идентификатора клиента.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-155">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="e5b6a-156">Для этого партнер поддерживает конфигурацию на своем окончании (вручную или через портал в рамках встроенной Организации поставщиков на платформу взаимодействия).</span><span class="sxs-lookup"><span data-stu-id="e5b6a-156">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="e5b6a-157">Рабочий процесс проверки подлинности и маршрутизации показан ниже.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-157">The Authentication and Routing workflow is shown below:</span></span>

![Схема рабочего процесса маршрутизации и проверки подлинности](../../media/Patient-app-6.png)

1. <span data-ttu-id="e5b6a-159">Запрос маркера доступа к приложению путем отправки:</span><span class="sxs-lookup"><span data-stu-id="e5b6a-159">Request for app access token by sending:</span></span>
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. <span data-ttu-id="e5b6a-160">Ответьте на маркер приложения:</span><span class="sxs-lookup"><span data-stu-id="e5b6a-160">Reply with an app token:</span></span>

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. <span data-ttu-id="e5b6a-161">Запросите защищенные данные с помощью маркера доступа.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-161">Request protected data with Access token.</span></span>

4. <span data-ttu-id="e5b6a-162">Сообщение о проверке подлинности: выберите соответствующий сервер FHIR для маршрутизации из идентификатора клиента в области.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-162">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope.</span></span>

5. <span data-ttu-id="e5b6a-163">Отправляет данные, защищенные приложением, от авторизованного сервера FHIR после проверки подлинности с помощью маркера приложения.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-163">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="e5b6a-164">Приклад</span><span class="sxs-lookup"><span data-stu-id="e5b6a-164">Interfaces</span></span>

<span data-ttu-id="e5b6a-165">Специальные вызовы и поля, используемые приложением пациентов, описаны в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-165">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="e5b6a-166">Выберите интерфейс, применимый к интерфейсам API FHIR и FHIR сервера.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-166">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="e5b6a-167">Характеристики интерфейса DSTU2</span><span class="sxs-lookup"><span data-stu-id="e5b6a-167">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="e5b6a-168">Характеристики интерфейса STU3</span><span class="sxs-lookup"><span data-stu-id="e5b6a-168">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="e5b6a-169">Производительность и надежность</span><span class="sxs-lookup"><span data-stu-id="e5b6a-169">Performance and Reliability</span></span>

<span data-ttu-id="e5b6a-170">Несмотря на то, что приложение пациентов в закрытом предварительном просмотре, нет гарантии на производительность "на конец".</span><span class="sxs-lookup"><span data-stu-id="e5b6a-170">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="e5b6a-171">Факторы, влияющие на производительность, включают относительную задержку всех переходов, участвующих в рабочем процессе, начиная с EHR в среде системы работоспособности и до партнера по взаимодействию, включая сервер FHIR и в приложение Office 365 для экосистемы и пациентов.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-171">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![Иллюстрация производительности партнеров по взаимодействию](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="e5b6a-173">Начало работы с FHIR</span><span class="sxs-lookup"><span data-stu-id="e5b6a-173">Get started with FHIR</span></span>  

<span data-ttu-id="e5b6a-174">Если вы новичок в FHIR и вам нужно легко получить доступ к серверу FHIR, который можно использовать для интерфейса интеграции Microsoft Teams EHR, корпорация Майкрософт предоставляет доступ к серверу FHIR с открытым исходным кодом для всех разработчиков.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-174">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="e5b6a-175">Ознакомьтесь со статьей " [что такое сервер FHIR для Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) ", чтобы узнать больше о сервере Open Source FHIR, доступном в Microsoft, и его развертывании для организаций.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-175">Please see the [What is FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="e5b6a-176">Вы также можете использовать среду HSPC Open песочницы EHR, чтобы создать EHR, который также поддерживает открытый сервер FHIR и использовать его для воспроизведения с помощью приложения пациентов.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-176">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="e5b6a-177">Мы рекомендуем ознакомиться с [документацией по программной среде HSPC](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span><span class="sxs-lookup"><span data-stu-id="e5b6a-177">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="e5b6a-178">Среда выполнения не только предоставляет простой, ориентированный на пользовательский интерфейс и удобный способ создания, добавления и редактирования пациентов, он также предоставляет несколько образцов для начала работы.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-178">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span> 
