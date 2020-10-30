---
title: Интерфейс STU3 пациентов для приложений и EHR интеграции
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
description: Сведения о том, как интегрировать электронные записи о работоспособности в приложение Microsoft Teams пациентов и спецификацию интерфейса STU3.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e20619badb2509d0a90f396563a98796e718e2f
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803497"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="57563-103">Характеристики интерфейса STU3</span><span class="sxs-lookup"><span data-stu-id="57563-103">STU3 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="57563-104">Действительно 30 октября 2020 г. приложение пациентов было прекращено и заменено [приложением "списки](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) " в Teams.</span><span class="sxs-lookup"><span data-stu-id="57563-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="57563-105">Данные приложения пациентов хранятся в почтовом ящике группы Office 365, которая является резервной командой.</span><span class="sxs-lookup"><span data-stu-id="57563-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="57563-106">Все данные, связанные с приложением пациентов, сохраняются в этой группе, но их больше нельзя будет получить с помощью пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="57563-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="57563-107">Пользователи могут повторно создавать списки с помощью приложения " [списки](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)".</span><span class="sxs-lookup"><span data-stu-id="57563-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="57563-108">Благодаря спискам, благодаря вашим командам в организации здравоохранения вы сможете создавать списки пациент для сценариев, начиная с округляющих и interdisciplinaryных собраний групп и заканчивая общим мониторингом пациента.</span><span class="sxs-lookup"><span data-stu-id="57563-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="57563-109">Чтобы приступить к работе, изучите шаблон пациентов в списках.</span><span class="sxs-lookup"><span data-stu-id="57563-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="57563-110">Дополнительные сведения об управлении приложением Lists в Организации можно найти в разделе [Управление приложением "списки"](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="57563-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="57563-111">Настройка или перенастройка сервера FHIR для работы с приложением Microsoft Teams пациентов требует понимания данных, к которым приложению требуется доступ.</span><span class="sxs-lookup"><span data-stu-id="57563-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="57563-112">Сервер FHIR должен поддерживать запросы POST, используя пакеты для указанных ниже ресурсов.</span><span class="sxs-lookup"><span data-stu-id="57563-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="57563-113">Подождите</span><span class="sxs-lookup"><span data-stu-id="57563-113">Patient</span></span>](#patient)
- [<span data-ttu-id="57563-114">Наблюдение</span><span class="sxs-lookup"><span data-stu-id="57563-114">Observation</span></span>](#observation)
- [<span data-ttu-id="57563-115">Условие</span><span class="sxs-lookup"><span data-stu-id="57563-115">Condition</span></span>](#condition)
- [<span data-ttu-id="57563-116">Происходит</span><span class="sxs-lookup"><span data-stu-id="57563-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="57563-117">Недопустимый Allergy</span><span class="sxs-lookup"><span data-stu-id="57563-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="57563-118">Приложения</span><span class="sxs-lookup"><span data-stu-id="57563-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="57563-119">[Оператор лечения](#medication-request) (заменяет MEDICATIONORDER в DSTU2 версии PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="57563-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="57563-120">Расположение (данные, необходимые для этого ресурса, могут быть включены в план)</span><span class="sxs-lookup"><span data-stu-id="57563-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="57563-121">Ресурс пациент является единственным обязательным ресурсом (без которого приложение не будет загружаться вообще); Тем не менее, рекомендуется, чтобы партнеры реализовали поддержку всех вышеупомянутых ресурсов для спецификаций, указанных ниже, для наилучшего взаимодействия с пользователем в приложении Microsoft Teams пациентов.</span><span class="sxs-lookup"><span data-stu-id="57563-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="57563-122">Запросы из приложения Microsoft Teams пациентов для более чем одного ресурса должны публиковать набор (пакет) запросов на URL-адрес сервера FHIR.</span><span class="sxs-lookup"><span data-stu-id="57563-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="57563-123">Сервер должен обрабатывать каждый запрос и возвращать набор ресурсов, соответствующих каждому запросу.</span><span class="sxs-lookup"><span data-stu-id="57563-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="57563-124">Дополнительные сведения и примеры можно найти в разделе [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="57563-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="57563-125">Оператор возможностей</span><span class="sxs-lookup"><span data-stu-id="57563-125">Capability Statement</span></span>

<span data-ttu-id="57563-126">Ниже указаны минимальные обязательные поля.</span><span class="sxs-lookup"><span data-stu-id="57563-126">These are the minimum required fields:</span></span>

 - <span data-ttu-id="57563-127">ДЕРЖИВАЕТ</span><span class="sxs-lookup"><span data-stu-id="57563-127">REST</span></span>

    - <span data-ttu-id="57563-128">Режиме</span><span class="sxs-lookup"><span data-stu-id="57563-128">Mode</span></span>
    - <span data-ttu-id="57563-129">Действует</span><span class="sxs-lookup"><span data-stu-id="57563-129">Interaction</span></span>
    - <span data-ttu-id="57563-130">Ресурс: тип</span><span class="sxs-lookup"><span data-stu-id="57563-130">Resource: Type</span></span>
    - <span data-ttu-id="57563-131">Безопасность: [расширение URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="57563-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
    
 - <span data-ttu-id="57563-132">FhirVersion (для нашего кода требуется, чтобы узнать, в какую версию следует поворачивать.)</span><span class="sxs-lookup"><span data-stu-id="57563-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="57563-133">[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="57563-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="57563-134">Подождите</span><span class="sxs-lookup"><span data-stu-id="57563-134">Patient</span></span>

<span data-ttu-id="57563-135">Ниже приведены минимальные обязательные поля, которые являются подмножеством полей профиля пациента Argonaut:</span><span class="sxs-lookup"><span data-stu-id="57563-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

 - <span data-ttu-id="57563-136">Name (имя). задано</span><span class="sxs-lookup"><span data-stu-id="57563-136">Name.Given</span></span>
 - <span data-ttu-id="57563-137">Family (имя)</span><span class="sxs-lookup"><span data-stu-id="57563-137">Name.Family</span></span>
 - <span data-ttu-id="57563-138">Полу</span><span class="sxs-lookup"><span data-stu-id="57563-138">Gender</span></span>
 - <span data-ttu-id="57563-139">Рождения</span><span class="sxs-lookup"><span data-stu-id="57563-139">BirthDate</span></span>
 - <span data-ttu-id="57563-140">MRN (идентификатор)</span><span class="sxs-lookup"><span data-stu-id="57563-140">MRN (Identifier)</span></span>

<span data-ttu-id="57563-141">В дополнение к [полям Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="57563-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="57563-142">Name. use</span><span class="sxs-lookup"><span data-stu-id="57563-142">Name.Use</span></span>
 - <span data-ttu-id="57563-143">Name. prefix</span><span class="sxs-lookup"><span data-stu-id="57563-143">Name.Prefix</span></span>
 - <span data-ttu-id="57563-144">[GeneralPractitioner]-ссылка GeneralPractitioner должна включаться в ресурс пациент (только для отображения поля)</span><span class="sxs-lookup"><span data-stu-id="57563-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="57563-145">Поиск ресурсов использует метод POST по адресу/Patient/_search и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="57563-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="57563-146">номер</span><span class="sxs-lookup"><span data-stu-id="57563-146">id</span></span>
 - <span data-ttu-id="57563-147">Family = (Поиск всех пациентов, чье имя семейства не содержало значение)</span><span class="sxs-lookup"><span data-stu-id="57563-147">family=(searches for all patients whose family name contains the value)</span></span>
 - <span data-ttu-id="57563-148">указанный =\<substring></span><span class="sxs-lookup"><span data-stu-id="57563-148">given=\<substring></span></span>
 - <span data-ttu-id="57563-149">Дата рождения = (точное совпадение)</span><span class="sxs-lookup"><span data-stu-id="57563-149">birthdate=(exact match)</span></span>
 - <span data-ttu-id="57563-150">Gender = (значения являются одним из административных пола)</span><span class="sxs-lookup"><span data-stu-id="57563-150">gender=(values being one of the administrative-gender)</span></span>
 - <span data-ttu-id="57563-151">\_Count (максимальное количество возвращаемых результатов)</span><span class="sxs-lookup"><span data-stu-id="57563-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="57563-152">Ответ должен содержать общее количество записей, возвращенных в результате поиска, и \_ счетчик будет использоваться PatientsApp, чтобы ограничить количество возвращаемых записей.</span><span class="sxs-lookup"><span data-stu-id="57563-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="57563-153">Идентификатор =\<mrn></span><span class="sxs-lookup"><span data-stu-id="57563-153">identifier=\<mrn></span></span>

<span data-ttu-id="57563-154">Цель — найти и отфильтровать пациента в пациент, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="57563-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="57563-155">ID: это идентификатор ресурса, который содержит каждый ресурс в FHIR.</span><span class="sxs-lookup"><span data-stu-id="57563-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="57563-156">MRN: фактический идентификатор пациента, который будет знать Clinical сотрудника.</span><span class="sxs-lookup"><span data-stu-id="57563-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="57563-157">Мы понимаем, что этот MRN основывается на типе идентификатора в ресурсе идентификатора в FHIR.</span><span class="sxs-lookup"><span data-stu-id="57563-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="57563-158">Имя</span><span class="sxs-lookup"><span data-stu-id="57563-158">Name</span></span>
- <span data-ttu-id="57563-159">Рождения</span><span class="sxs-lookup"><span data-stu-id="57563-159">Birthdate</span></span>

<span data-ttu-id="57563-160">Посмотрите следующий пример звонка:</span><span class="sxs-lookup"><span data-stu-id="57563-160">See the following example of the call:</span></span>

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=ruth&family=black

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "meta": {
    "lastUpdated": "2019-01-14T23:44:45.052+00:00"
  },
  "type": "searchset",
  "total": 1,
  "link": [
    {
      "relation": "self",
      "url": <fhir-server>/Patient/_search"
    }
  ],
  "entry": [
    {
      "fullUrl": <fhir-server>/Patient/<patient-id>",
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "meta": {
          "versionId": "1",
          "lastUpdated": "2017-10-18T18:32:37.000+00:00"
        },
        "text": {
          "status": "generated",
          "div": "<div>\n        <p>Ruth Black</p>\n      </div>"
        },
        "identifier": [
          {
            "use": "usual",
            "type": {
              "coding": [
                {
                  "system": "https://hl7.org/fhir/v2/0203",
                  "code": "MR",
                  "display": "Medical record number",
                  "userSelected": false
                }
              ],
              "text": "Medical record number"
            },
            "system": "http://hospital.smarthealthit.org",
            "value": "1234567"
          }
        ],
        "active": true,
        "name": [
          {
            "use": "official",
            "family": "Black",
            "given": [
              "Ruth",
              "C."
            ]
          }
        ],
        "telecom": [
          {
            "system": "phone",
            "value": "800-599-2739",
            "use": "home"
          },
          {
            "system": "phone",
            "value": "800-808-7785",
            "use": "mobile"
          },
          {
            "system": "email",
            "value": "ruth.black@example.com"
          }
        ],
        "gender": "female",
        "birthDate": "1951-08-23",
        "address": [
          {
            "use": "home",
            "line": [
              "26 South RdApt 22"
            ],
            "city": "Sapulpa",
            "state": "OK",
            "postalCode": "74066",
            "country": "USA"
          }
        ]
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

```
Request:
GET <fhir-server>/Patient/<patient-id>

Response:
{
  "resourceType": "Patient",
  "id": "<patient-id>",
  "identifier": [
    {
      "use": "usual",
      "type": {
        "coding": [
          {
            "system": "https://hl7.org/fhir/v2/0203",
            "code": "MR",
          }
        ],
        "text": "Medical record number"
      },
      "value": "1234567"
    }
  ],
  "name": [
    {
      "use": "official",
      "family": "Adams",
      "given": [ "Daniel", "X." ]
    }
  ],
  "gender": "male",
  "birthDate": "1925-12-23",
}
```

<span data-ttu-id="57563-161">[https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="57563-161">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="57563-162">Наблюдение</span><span class="sxs-lookup"><span data-stu-id="57563-162">Observation</span></span>

<span data-ttu-id="57563-163">Это минимальные обязательные поля, которые являются подмножеством [профиля Argonaut Vital-Signs](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span><span class="sxs-lookup"><span data-stu-id="57563-163">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

 - <span data-ttu-id="57563-164">Эффективная (Дата и время)</span><span class="sxs-lookup"><span data-stu-id="57563-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="57563-165">Код. кодирование. Code</span><span class="sxs-lookup"><span data-stu-id="57563-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="57563-166">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="57563-166">ValueQuantity.Value</span></span>

<span data-ttu-id="57563-167">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="57563-167">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="57563-168">Код. программирование. Display</span><span class="sxs-lookup"><span data-stu-id="57563-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="57563-169">ValueQuantity. ед.</span><span class="sxs-lookup"><span data-stu-id="57563-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="57563-170">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="57563-170">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="57563-171">пациент =\<patient id></span><span class="sxs-lookup"><span data-stu-id="57563-171">patient=\<patient id></span></span>
 - <span data-ttu-id="57563-172">_sort =-Дата</span><span class="sxs-lookup"><span data-stu-id="57563-172">_sort=-date</span></span>
 - <span data-ttu-id="57563-173">Category (мы будем запрашивать "Category =", чтобы получить список важных знаков.</span><span class="sxs-lookup"><span data-stu-id="57563-173">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="57563-174">Ниже приведен пример звонка.</span><span class="sxs-lookup"><span data-stu-id="57563-174">Refer to this example of the call:</span></span>

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 20,
  "entry": [
    {
      "resource": {
        "resourceType": "Observation",
        "id": "<resource-id>",
        "category": [
          {
            "coding": [
              {
                "system": "https://hl7.org/fhir/observation-category",
                "code": "vital-signs"
              }
            ],
          }
        ],
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "8867-4",
              "display": "heart_rate"
            }
          ]
        },
        "effectiveDateTime": "2009-04-08T00:00:00-06:00",
        "valueQuantity": {
          "value": 72.0,
          "unit": "{beats}/min",
          "system": "http://unitsofmeasure.org",
        }
      }
    },
    .
    .
    .
  ]
}
```

<span data-ttu-id="57563-175">[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="57563-175">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="57563-176">Условие</span><span class="sxs-lookup"><span data-stu-id="57563-176">Condition</span></span>

<span data-ttu-id="57563-177">Ниже приведено минимально необходимое поле, которое является подмножеством [профиля условия Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span><span class="sxs-lookup"><span data-stu-id="57563-177">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

 - <span data-ttu-id="57563-178">Код. кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="57563-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="57563-179">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="57563-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="57563-180">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="57563-180">AssertedDate</span></span>
 - <span data-ttu-id="57563-181">Уровню серьезности</span><span class="sxs-lookup"><span data-stu-id="57563-181">Severity</span></span>

<span data-ttu-id="57563-182">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="57563-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="57563-183">пациент =\<patient id></span><span class="sxs-lookup"><span data-stu-id="57563-183">patient=\<patient id></span></span>
 - <span data-ttu-id="57563-184">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="57563-184">_count=\<max results></span></span>

<span data-ttu-id="57563-185">Ниже приведен пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="57563-185">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/Condition?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 2,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "185903001",
              "display": "Needs influenza immunization",
            }
          ]
        },
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        },
        "assertedDate": "2018-04-04"
      }
    },
    .
    .
    .
  ]
}
```

<span data-ttu-id="57563-186">[https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="57563-186">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="57563-187">Происходит</span><span class="sxs-lookup"><span data-stu-id="57563-187">Encounter</span></span>

<span data-ttu-id="57563-188">Это минимальные обязательные поля, которые являются подмножеством подмножества [основного профиля](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) , которое должно иметь "поля".</span><span class="sxs-lookup"><span data-stu-id="57563-188">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

 - <span data-ttu-id="57563-189">Состояни</span><span class="sxs-lookup"><span data-stu-id="57563-189">Status</span></span>
 - <span data-ttu-id="57563-190">Введите [0]. Кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="57563-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="57563-191">Кроме того, ниже перечислены поля, которые можно получить из основных полей "требуется поддержка" для профиля в США.</span><span class="sxs-lookup"><span data-stu-id="57563-191">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

 - <span data-ttu-id="57563-192">Period. Start</span><span class="sxs-lookup"><span data-stu-id="57563-192">Period.Start</span></span>
 - <span data-ttu-id="57563-193">Расположение [0]. Расположение. Display</span><span class="sxs-lookup"><span data-stu-id="57563-193">Location[0].Location.Display</span></span>

<span data-ttu-id="57563-194">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="57563-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="57563-195">пациент =\<patient id></span><span class="sxs-lookup"><span data-stu-id="57563-195">patient=\<patient id></span></span>
 - <span data-ttu-id="57563-196">_sort: DESC =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="57563-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="57563-197">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="57563-197">_count=\<max results></span></span>

<span data-ttu-id="57563-198">Цель — получить Последнее известное расположение пациента.</span><span class="sxs-lookup"><span data-stu-id="57563-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="57563-199">Каждый из этих обнаружений ссылается на ресурс расположения.</span><span class="sxs-lookup"><span data-stu-id="57563-199">Each encounter references a location resource.</span></span> <span data-ttu-id="57563-200">Ссылка также должна включать поле отображения местоположения.</span><span class="sxs-lookup"><span data-stu-id="57563-200">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="57563-201">[https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="57563-201">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="57563-202">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="57563-202">AllergyIntolerance</span></span>

<span data-ttu-id="57563-203">Это минимальные обязательные поля, которые являются подмножеством профиля [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :</span><span class="sxs-lookup"><span data-stu-id="57563-203">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

 - <span data-ttu-id="57563-204">Code. Text</span><span class="sxs-lookup"><span data-stu-id="57563-204">Code.Text</span></span>
 - <span data-ttu-id="57563-205">Код. кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="57563-205">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="57563-206">ClinicalStatus/VerificationStatus (мы прочитали оба)</span><span class="sxs-lookup"><span data-stu-id="57563-206">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="57563-207">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также может прочитать следующее поле:</span><span class="sxs-lookup"><span data-stu-id="57563-207">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

 - <span data-ttu-id="57563-208">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="57563-208">AssertedDate</span></span>
 - <span data-ttu-id="57563-209">Примечание. текст</span><span class="sxs-lookup"><span data-stu-id="57563-209">Note.Text</span></span>
 - <span data-ttu-id="57563-210">Реакция</span><span class="sxs-lookup"><span data-stu-id="57563-210">Reaction</span></span>
    - <span data-ttu-id="57563-211">Вещество (один элемент кодирования)</span><span class="sxs-lookup"><span data-stu-id="57563-211">Substance (one coding element)</span></span>
    - <span data-ttu-id="57563-212">Манифест (один элемент кодирования)</span><span class="sxs-lookup"><span data-stu-id="57563-212">Manifestation (one coding element)</span></span>

<span data-ttu-id="57563-213">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="57563-213">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="57563-214">Пациент =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="57563-214">Patient =  \<patient id></span></span>

<span data-ttu-id="57563-215">Посмотрите следующий пример звонка:</span><span class="sxs-lookup"><span data-stu-id="57563-215">See the following example of the call:</span></span> 

```
Request:
GET <fhir-server>/AllergyIntolerance?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "AllergyIntolerance",
        "id": "<resource-id>",
        "clinicalStatus": "active",
        "verificationStatus": "confirmed",
        "code": {
          "coding": [
            {
              "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",
              "code": "N0000175503",
              "display": "sulfonamide antibacterial",
            }
          ],
          "text": "sulfonamide antibacterial"
        },
        "assertedDate": "2018-01-01T00:00:00-07:00",
        "reaction": [
          {
            "manifestation": [
              {
                "coding": [
                  {
                    "system": "http://snomed.info/sct",
                    "code": "271807003",
                    "display": "skin rash",
                  }
                ],
                "text": "skin rash"
              }
            ],
          }
        ]
      }
    }
  ]
}
```

<span data-ttu-id="57563-216">[https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="57563-216">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="57563-217">Запрос лечения</span><span class="sxs-lookup"><span data-stu-id="57563-217">Medication Request</span></span>

<span data-ttu-id="57563-218">Ниже указаны минимальные обязательные поля, которые являются подмножеством [профиля запроса "основной лечения" США](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html).</span><span class="sxs-lookup"><span data-stu-id="57563-218">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

 - <span data-ttu-id="57563-219">Лечения. Display (если ссылка)</span><span class="sxs-lookup"><span data-stu-id="57563-219">Medication.Display (if Reference)</span></span>
 - <span data-ttu-id="57563-220">Лечения. Text (если CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="57563-220">Medication.Text (if CodableConcept)</span></span>
 - <span data-ttu-id="57563-221">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="57563-221">AuthoredOn</span></span>
 - <span data-ttu-id="57563-222">Запросивший. агент. Display</span><span class="sxs-lookup"><span data-stu-id="57563-222">Requester.Agent.Display</span></span>

<span data-ttu-id="57563-223">В дополнение к полям "основные" в США для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="57563-223">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="57563-224">DosageInstruction[..]. Текстовые</span><span class="sxs-lookup"><span data-stu-id="57563-224">DosageInstruction[..].Text</span></span>
 - <span data-ttu-id="57563-225">Текстовые</span><span class="sxs-lookup"><span data-stu-id="57563-225">Text</span></span>

<span data-ttu-id="57563-226">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="57563-226">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="57563-227">пациент =\<patient id></span><span class="sxs-lookup"><span data-stu-id="57563-227">patient=\<patient id></span></span>
 - <span data-ttu-id="57563-228">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="57563-228">_count=\<max results></span></span>

<span data-ttu-id="57563-229">[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="57563-229">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="57563-230">Приложения</span><span class="sxs-lookup"><span data-stu-id="57563-230">Coverage</span></span>

<span data-ttu-id="57563-231">Это минимальный обязательный набор полей, не охваченных профилями США или Argonaut:</span><span class="sxs-lookup"><span data-stu-id="57563-231">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="57563-232">Группировка, по крайней мере один элемент с</span><span class="sxs-lookup"><span data-stu-id="57563-232">Grouping, at least one element with</span></span>
    - <span data-ttu-id="57563-233">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="57563-233">GroupDisplay</span></span>
    - <span data-ttu-id="57563-234">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="57563-234">PlanDisplay</span></span>
 - <span data-ttu-id="57563-235">Срока</span><span class="sxs-lookup"><span data-stu-id="57563-235">Period</span></span>
 - <span data-ttu-id="57563-236">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="57563-236">SubscriberId</span></span>

<span data-ttu-id="57563-237">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="57563-237">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="57563-238">Пациент = \<patient id></span><span class="sxs-lookup"><span data-stu-id="57563-238">Patient = \<patient id></span></span>

<span data-ttu-id="57563-239">[https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="57563-239">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
