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
description: Узнайте, как интегрировать электронные медицинские записи в приложение "Пациенты" Microsoft Teams с помощью API FHIR.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 594375959a8cd7cbbfc21c6b9d5ceb6c0f8a8dac
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803547"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="8525b-103">Интеграция электронных историй болезни в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8525b-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="8525b-104">С 30 октября 2020 г. приложение "Пациенты" [](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) было отменено и заменено приложением "Списки" в Teams.</span><span class="sxs-lookup"><span data-stu-id="8525b-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="8525b-105">Данные приложения "Пациенты" хранятся в почтовом ящике группы Office 365, которая сохраняет данные команды.</span><span class="sxs-lookup"><span data-stu-id="8525b-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="8525b-106">Все данные, связанные с приложением "Пациенты", сохраняются в этой группе, но к ним нельзя получить доступ через пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="8525b-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="8525b-107">Пользователи могут создавать списки повторно с помощью приложения ["Списки".](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)</span><span class="sxs-lookup"><span data-stu-id="8525b-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="8525b-108">С помощью списков группы обслуживания в вашей организации здравоохранения могут создавать списки пациентов для сценариев, которые могут быть: от округов и межпрофиленных собраний до общего наблюдения пациентов.</span><span class="sxs-lookup"><span data-stu-id="8525b-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="8525b-109">Чтобы начать, ознакомьтесь с шаблоном "Пациенты" в списке.</span><span class="sxs-lookup"><span data-stu-id="8525b-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="8525b-110">Дополнительные информацию об управлении приложением "Списки" в организации см. в приложении ["Управление списками".](../../manage-lists-app.md)</span><span class="sxs-lookup"><span data-stu-id="8525b-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="8525b-111">Эта статья предназначена для ИТ-разработчиков в области здравоохранения, заинтересованных в использовании API FHIR в верхней части системы медицинских данных для подключения к Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8525b-111">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="8525b-112">Это позволит обеспечить координацию работы по сфере здравоохранения, которые соответствуют потребностям организации здравоохранения.</span><span class="sxs-lookup"><span data-stu-id="8525b-112">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="8525b-113">В следующих статьях данная статья содержит спецификации интерфейса FHIR для приложения "Пациенты" Microsoft Teams, а также в следующих разделах объясняется, что необходимо для настройки сервера FHIR и подключения к приложению "Пациенты" в среде разработки или клиенте.</span><span class="sxs-lookup"><span data-stu-id="8525b-113">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="8525b-114">Кроме того, вам потребуется ознакомиться с документацией выбранного сервера FHIR, который должен быть одним из поддерживаемых вариантов:</span><span class="sxs-lookup"><span data-stu-id="8525b-114">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>

- <span data-ttu-id="8525b-115">Datica (в рамках [предложения CMI)](https://datica.com/compliant-managed-integration/)</span><span class="sxs-lookup"><span data-stu-id="8525b-115">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="8525b-116">Infor Cloverleaf (через мост [Infor FHIR)](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)</span><span class="sxs-lookup"><span data-stu-id="8525b-116">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="8525b-117">Redox (через [сервер R^FHIR)](https://www.redoxengine.com/fhir/)</span><span class="sxs-lookup"><span data-stu-id="8525b-117">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="8525b-118">Dapasoft (через [Corolar on FHIR)](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)</span><span class="sxs-lookup"><span data-stu-id="8525b-118">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="8525b-119">Этот процесс не включает шаги, которые включают в себя центр администрирования Microsoft Teams или командлеты PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8525b-119">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="8525b-120">Настройка полностью происходит на стороне сервера или службы FHIR, а также в клиенте приложения "Пациенты".</span><span class="sxs-lookup"><span data-stu-id="8525b-120">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="8525b-121">Ниже приведена архитектура приложения "Пациенты":</span><span class="sxs-lookup"><span data-stu-id="8525b-121">Illustrated below is the architecture of the Patients app:</span></span>

![Схема архитектуры приложения "Пациенты"](../../media/patients-app-architecture.png)

<span data-ttu-id="8525b-123">В следующих разделах объясняется, что для интеграции с приложением "Пациенты" должен соответствовать уровень доступа только для данных FHIR для приложения "Пациенты", который должен выполняться для интеграции с приложением "Пациенты" сервером FHIR (или API С ПОДДЕРЖКОЙ FHIR):</span><span class="sxs-lookup"><span data-stu-id="8525b-123">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="8525b-124">Ожидания проверки подлинности пользователей</span><span class="sxs-lookup"><span data-stu-id="8525b-124">Expectations around user authentication</span></span>
- <span data-ttu-id="8525b-125">Функциональные и технические требования интерфейса интеграции</span><span class="sxs-lookup"><span data-stu-id="8525b-125">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="8525b-126">Ожидания производительности и надежности</span><span class="sxs-lookup"><span data-stu-id="8525b-126">Expectations around performance and reliability</span></span>
- <span data-ttu-id="8525b-127">Ожидания по ресурсам, которые будут поддерживаться с помощью FHIR для приложения "Пациенты"</span><span class="sxs-lookup"><span data-stu-id="8525b-127">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="8525b-128">Процесс интеграции и ожидаемая модель взаимодействия</span><span class="sxs-lookup"><span data-stu-id="8525b-128">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="8525b-129">Начало работы с FHIR и некоторые распространенные проблемы, с которыми сталкиваются приложения "Пациенты"</span><span class="sxs-lookup"><span data-stu-id="8525b-129">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="8525b-130">Будущие требования для следующей итерации приложения "Пациенты"</span><span class="sxs-lookup"><span data-stu-id="8525b-130">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="8525b-131">В следующих разделах слово "партнер" или "партнер interop" используется для ссылки на сторонние организации, которые обеспечивают интеграцию с системами EHR для приложения "Пациенты" с помощью FHIR и внедряют сервер FHIR в соответствии со спецификациями, указанными в списке.</span><span class="sxs-lookup"><span data-stu-id="8525b-131">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="8525b-132">Функциональные и технические требования</span><span class="sxs-lookup"><span data-stu-id="8525b-132">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="8525b-133">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="8525b-133">Authentication</span></span>  

<span data-ttu-id="8525b-134">Авторизация на  уровне приложения без поддержки авторизации на уровне пользователя — это наиболее распространенный способ выполнения преобразований данных и передачи подключений к данным EHR с помощью FHIR, хотя система EHR может реализовать авторизацию на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="8525b-134">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="8525b-135">Службе Interop Service (Partner) предоставляется повышенный доступ к данным EHR, и когда они выставляют те же данные, что и ресурсы FHIR, контекст авторизации не передается interop Service Consumer (приложение Patients), интегрированному со службой Interop Service или Платформой.</span><span class="sxs-lookup"><span data-stu-id="8525b-135">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="8525b-136">Приложение "Пациенты" не сможет принудительно выполнять авторизацию на уровне пользователя, но поддерживает приложение для проверки подлинности приложений между приложением "Пациенты" и службой партнера Interop.</span><span class="sxs-lookup"><span data-stu-id="8525b-136">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner's service.</span></span>

<span data-ttu-id="8525b-137">Модель проверки подлинности "Приложения к приложениям" описана ниже.</span><span class="sxs-lookup"><span data-stu-id="8525b-137">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="8525b-138">Для проверки подлинности службы необходимо использовать поток [](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)учетных данных клиента OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="8525b-138">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="8525b-139">Служба партнера должна предоставлять следующие услуги:</span><span class="sxs-lookup"><span data-stu-id="8525b-139">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="8525b-140">Служба партнеров позволяет приложению "Пациенты" создать учетную запись партнера, которая позволяет приложению "Пациенты" создавать и создавать собственные учетные записи client_id и client_secret, управлять которыми можно с помощью портала проверки подлинности на сервере проверки подлинности партнера.</span><span class="sxs-lookup"><span data-stu-id="8525b-140">The Partner service enables the Patients app to create an account with the Partner, which enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner's Authentication server.</span></span>

2. <span data-ttu-id="8525b-141">Партнерская служба владеет системой проверки подлинности и авторизации, которая проверяет предоставленные учетные данные клиента и возвращает маркер доступа с подсказкой клиента (как описано ниже).</span><span class="sxs-lookup"><span data-stu-id="8525b-141">The Partner service owns the Authentication/Authorization system, which accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>

3. <span data-ttu-id="8525b-142">По соображениям безопасности или в случае секретного нарушения приложение "Пациенты" может повторно создать секрет, сделать ее недействительной или удалить старую секретную (такой же пример доступен на портале Azure — регистрация приложений AAD).</span><span class="sxs-lookup"><span data-stu-id="8525b-142">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (example of the same is available in Azure Portal - AAD App Registration).</span></span>

4. <span data-ttu-id="8525b-143">Конечная точка метаданных с заявлением о соответствии должна быть без проверки подлинности, она должна быть доступна без маркера проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="8525b-143">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>

5. <span data-ttu-id="8525b-144">Служба партнеров предоставляет конечную точку маркера для приложения "Пациенты" для запроса маркера доступа с помощью потока учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="8525b-144">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="8525b-145">URL-адрес маркера для каждого сервера авторизации должен быть частью заявления о соответствии (возможности) FHIR, извлекаемого из метаданных на сервере FHIR, как в этом примере:</span><span class="sxs-lookup"><span data-stu-id="8525b-145">The token URL as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

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

<span data-ttu-id="8525b-146">Запрос маркера доступа состоит из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="8525b-146">A request for an access token consists of the following parameters:</span></span>

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

<span data-ttu-id="8525b-147">Партнерская служба предоставляет приложение client_id и client_secret для пациентов, управляемое через портал регистрации через веб-сайт со стороны партнера.</span><span class="sxs-lookup"><span data-stu-id="8525b-147">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner's side.</span></span> <span data-ttu-id="8525b-148">Служба партнеров предоставляет конечную точку для запроса маркера доступа с помощью потока учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="8525b-148">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="8525b-149">Для успешного отклика необходимо включить token_type, access_token и expires_in параметры.</span><span class="sxs-lookup"><span data-stu-id="8525b-149">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="8525b-150">Маршрутирование: сопоставление клиента AAD с конечной точкой поставщика</span><span class="sxs-lookup"><span data-stu-id="8525b-150">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="8525b-151">Приложение "Пациенты" подключается к партнерской службе через одну конечную точку.</span><span class="sxs-lookup"><span data-stu-id="8525b-151">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="8525b-152">Партнерская служба владеет и ведет механизм для связи каждого клиента Майкрософт (AAD-ИД клиента) с соответствующим поставщиком услуг здравоохранения (FHIR-сервером), с помощью которых работает партнерская служба.</span><span class="sxs-lookup"><span data-stu-id="8525b-152">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="8525b-153">Сопоставление клиента AAD с конечной точкой поставщика использует его ИД (GUID).</span><span class="sxs-lookup"><span data-stu-id="8525b-153">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="8525b-154">Приложение "Пациенты" передает ИД клиента в области действия, запрашивая маркер доступа для каждого запроса.</span><span class="sxs-lookup"><span data-stu-id="8525b-154">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="8525b-155">Служба партнеров сохраняет сопоставление ИД клиента с конечной точкой поставщика и перенаправляет запросы в конечную точку поставщика на основе его ИД клиента.</span><span class="sxs-lookup"><span data-stu-id="8525b-155">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="8525b-156">Для этого партнеры по-своему поддерживают конфигурацию (вручную или через портал в рамках передачи организаций-поставщиков на свою платформу Interop).</span><span class="sxs-lookup"><span data-stu-id="8525b-156">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="8525b-157">Ниже показан рабочий процесс проверки подлинности и маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="8525b-157">The Authentication and Routing workflow is shown below:</span></span>

![Схема рабочего процесса проверки подлинности и маршрутизации](../../media/Patient-app-6.png)

1. <span data-ttu-id="8525b-159">Запрос маркера доступа приложения с помощью отправки:</span><span class="sxs-lookup"><span data-stu-id="8525b-159">Request for app access token by sending:</span></span>
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. <span data-ttu-id="8525b-160">Ответ с помощью маркера приложения:</span><span class="sxs-lookup"><span data-stu-id="8525b-160">Reply with an app token:</span></span>

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. <span data-ttu-id="8525b-161">Запрос защищенных данных с помощью маркера Access.</span><span class="sxs-lookup"><span data-stu-id="8525b-161">Request protected data with Access token.</span></span>

4. <span data-ttu-id="8525b-162">Сообщение о авторизации: выберите нужный сервер FHIR для маршрутизации из ИД клиента в области.</span><span class="sxs-lookup"><span data-stu-id="8525b-162">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope.</span></span>

5. <span data-ttu-id="8525b-163">Отправляет защищенные приложение данные с авторизованнго сервера FHIR после проверки подлинности с помощью маркера приложения.</span><span class="sxs-lookup"><span data-stu-id="8525b-163">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="8525b-164">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="8525b-164">Interfaces</span></span>

<span data-ttu-id="8525b-165">Конкретные вызовы и поля, используемые приложением "Пациенты", описаны в следующих статьях.</span><span class="sxs-lookup"><span data-stu-id="8525b-165">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="8525b-166">Выберите интерфейс, соответствующий API сервера FHIR или FHIR.</span><span class="sxs-lookup"><span data-stu-id="8525b-166">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="8525b-167">Характеристики интерфейса DSTU2</span><span class="sxs-lookup"><span data-stu-id="8525b-167">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="8525b-168">Характеристики интерфейса STU3</span><span class="sxs-lookup"><span data-stu-id="8525b-168">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="8525b-169">Производительность и надежность</span><span class="sxs-lookup"><span data-stu-id="8525b-169">Performance and Reliability</span></span>

<span data-ttu-id="8525b-170">Пока приложение "Пациенты" находится в режиме личной предварительной версии, нет никаких гарантий производительности.</span><span class="sxs-lookup"><span data-stu-id="8525b-170">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="8525b-171">К факторам, влияющим на производительность, относятся относительные задержки всех переходов рабочего процесса, начиная от EHR в среде системы здравоохранения до партнера по работе с interop, включая сервер FHIR и приложение "Пациенты" в Office 365.</span><span class="sxs-lookup"><span data-stu-id="8525b-171">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![Изображение производительности партнеров Interop](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="8525b-173">Начало работы с FHIR</span><span class="sxs-lookup"><span data-stu-id="8525b-173">Get started with FHIR</span></span>  

<span data-ttu-id="8525b-174">Если вы впервые используете службу FHIR и вам нужен простой доступ к серверу FHIR, который можно использовать с интерфейсом интеграции Microsoft Teams EHR, все разработчики могут использовать сервер FHIR с открытым кодом.</span><span class="sxs-lookup"><span data-stu-id="8525b-174">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="8525b-175">Дополнительные данные о сервере FHIR Server с открытым кодом, который доступен корпорации Майкрософт, и его развертывании для организаций, см. в статье "Что такое [FHIR Server](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) для Azure".</span><span class="sxs-lookup"><span data-stu-id="8525b-175">Please see the [What is FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="8525b-176">Вы также можете использовать среду EHR Open HSPC для создания EHR, который также поддерживает открытый сервер FHIR, и использовать его для управления приложением "Пациенты".</span><span class="sxs-lookup"><span data-stu-id="8525b-176">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="8525b-177">Рекомендуем ознакомиться с документацией по песочнице [HSPC.](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)</span><span class="sxs-lookup"><span data-stu-id="8525b-177">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="8525b-178">Песочница не только обеспечивает простой, ориентированный на пользовательский интерфейс и простой способ создания, добавления и редактирования пациентов, но и предоставляет несколько примеров для начала работы.</span><span class="sxs-lookup"><span data-stu-id="8525b-178">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span> 
