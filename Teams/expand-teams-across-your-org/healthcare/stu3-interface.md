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
ms.openlocfilehash: a36c6176b4873dd41d654493bd36e9a3dbbfd49a
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772270"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="690d3-103">Характеристики интерфейса STU3</span><span class="sxs-lookup"><span data-stu-id="690d3-103">STU3 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="690d3-104">Действительно 30 октября 2020 г. приложение пациентов было прекращено и заменено [приложением "списки](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) " в Teams.</span><span class="sxs-lookup"><span data-stu-id="690d3-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="690d3-105">Благодаря спискам, благодаря вашим командам в организации здравоохранения вы сможете создавать списки пациент для сценариев, начиная с округляющих и interdisciplinaryных собраний групп и заканчивая общим мониторингом пациента.</span><span class="sxs-lookup"><span data-stu-id="690d3-105">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="690d3-106">Чтобы приступить к работе, изучите шаблон пациентов в списках.</span><span class="sxs-lookup"><span data-stu-id="690d3-106">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="690d3-107">Дополнительные сведения об управлении приложением Lists в Организации можно найти в разделе [Управление приложением "списки"](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="690d3-107">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="690d3-108">Настройка или перенастройка сервера FHIR для работы с приложением Microsoft Teams пациентов требует понимания данных, к которым приложению требуется доступ.</span><span class="sxs-lookup"><span data-stu-id="690d3-108">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="690d3-109">Сервер FHIR должен поддерживать запросы POST, используя пакеты для указанных ниже ресурсов.</span><span class="sxs-lookup"><span data-stu-id="690d3-109">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="690d3-110">Подождите</span><span class="sxs-lookup"><span data-stu-id="690d3-110">Patient</span></span>](#patient)
- [<span data-ttu-id="690d3-111">Наблюдение</span><span class="sxs-lookup"><span data-stu-id="690d3-111">Observation</span></span>](#observation)
- [<span data-ttu-id="690d3-112">Условие</span><span class="sxs-lookup"><span data-stu-id="690d3-112">Condition</span></span>](#condition)
- [<span data-ttu-id="690d3-113">Происходит</span><span class="sxs-lookup"><span data-stu-id="690d3-113">Encounter</span></span>](#encounter)
- [<span data-ttu-id="690d3-114">Недопустимый Allergy</span><span class="sxs-lookup"><span data-stu-id="690d3-114">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="690d3-115">Приложения</span><span class="sxs-lookup"><span data-stu-id="690d3-115">Coverage</span></span>](#coverage)
- <span data-ttu-id="690d3-116">[Оператор лечения](#medication-request) (заменяет MEDICATIONORDER в DSTU2 версии PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="690d3-116">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="690d3-117">Расположение (данные, необходимые для этого ресурса, могут быть включены в план)</span><span class="sxs-lookup"><span data-stu-id="690d3-117">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="690d3-118">Ресурс пациент является единственным обязательным ресурсом (без которого приложение не будет загружаться вообще); Тем не менее, рекомендуется, чтобы партнеры реализовали поддержку всех вышеупомянутых ресурсов для спецификаций, указанных ниже, для наилучшего взаимодействия с пользователем в приложении Microsoft Teams пациентов.</span><span class="sxs-lookup"><span data-stu-id="690d3-118">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="690d3-119">Запросы из приложения Microsoft Teams пациентов для более чем одного ресурса должны публиковать набор (пакет) запросов на URL-адрес сервера FHIR.</span><span class="sxs-lookup"><span data-stu-id="690d3-119">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="690d3-120">Сервер должен обрабатывать каждый запрос и возвращать набор ресурсов, соответствующих каждому запросу.</span><span class="sxs-lookup"><span data-stu-id="690d3-120">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="690d3-121">Дополнительные сведения и примеры можно найти в разделе [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="690d3-121">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="690d3-122">Оператор возможностей</span><span class="sxs-lookup"><span data-stu-id="690d3-122">Capability Statement</span></span>

<span data-ttu-id="690d3-123">Ниже указаны минимальные обязательные поля.</span><span class="sxs-lookup"><span data-stu-id="690d3-123">These are the minimum required fields:</span></span>

 - <span data-ttu-id="690d3-124">ДЕРЖИВАЕТ</span><span class="sxs-lookup"><span data-stu-id="690d3-124">REST</span></span>

    - <span data-ttu-id="690d3-125">Режиме</span><span class="sxs-lookup"><span data-stu-id="690d3-125">Mode</span></span>
    - <span data-ttu-id="690d3-126">Действует</span><span class="sxs-lookup"><span data-stu-id="690d3-126">Interaction</span></span>
    - <span data-ttu-id="690d3-127">Ресурс: тип</span><span class="sxs-lookup"><span data-stu-id="690d3-127">Resource: Type</span></span>
    - <span data-ttu-id="690d3-128">Безопасность: [расширение URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="690d3-128">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
    
 - <span data-ttu-id="690d3-129">FhirVersion (для нашего кода требуется, чтобы узнать, в какую версию следует поворачивать.)</span><span class="sxs-lookup"><span data-stu-id="690d3-129">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="690d3-130">[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="690d3-130">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="690d3-131">Подождите</span><span class="sxs-lookup"><span data-stu-id="690d3-131">Patient</span></span>

<span data-ttu-id="690d3-132">Ниже приведены минимальные обязательные поля, которые являются подмножеством полей профиля пациента Argonaut:</span><span class="sxs-lookup"><span data-stu-id="690d3-132">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

 - <span data-ttu-id="690d3-133">Name (имя). задано</span><span class="sxs-lookup"><span data-stu-id="690d3-133">Name.Given</span></span>
 - <span data-ttu-id="690d3-134">Family (имя)</span><span class="sxs-lookup"><span data-stu-id="690d3-134">Name.Family</span></span>
 - <span data-ttu-id="690d3-135">Полу</span><span class="sxs-lookup"><span data-stu-id="690d3-135">Gender</span></span>
 - <span data-ttu-id="690d3-136">Рождения</span><span class="sxs-lookup"><span data-stu-id="690d3-136">BirthDate</span></span>
 - <span data-ttu-id="690d3-137">MRN (идентификатор)</span><span class="sxs-lookup"><span data-stu-id="690d3-137">MRN (Identifier)</span></span>

<span data-ttu-id="690d3-138">В дополнение к [полям Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="690d3-138">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="690d3-139">Name. use</span><span class="sxs-lookup"><span data-stu-id="690d3-139">Name.Use</span></span>
 - <span data-ttu-id="690d3-140">Name. prefix</span><span class="sxs-lookup"><span data-stu-id="690d3-140">Name.Prefix</span></span>
 - <span data-ttu-id="690d3-141">[GeneralPractitioner]-ссылка GeneralPractitioner должна включаться в ресурс пациент (только для отображения поля)</span><span class="sxs-lookup"><span data-stu-id="690d3-141">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="690d3-142">Поиск ресурсов использует метод POST по адресу/Patient/_search и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="690d3-142">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="690d3-143">номер</span><span class="sxs-lookup"><span data-stu-id="690d3-143">id</span></span>
 - <span data-ttu-id="690d3-144">Family = (Поиск всех пациентов, чье имя семейства не содержало значение)</span><span class="sxs-lookup"><span data-stu-id="690d3-144">family=(searches for all patients whose family name contains the value)</span></span>
 - <span data-ttu-id="690d3-145">указанный =\<substring></span><span class="sxs-lookup"><span data-stu-id="690d3-145">given=\<substring></span></span>
 - <span data-ttu-id="690d3-146">Дата рождения = (точное совпадение)</span><span class="sxs-lookup"><span data-stu-id="690d3-146">birthdate=(exact match)</span></span>
 - <span data-ttu-id="690d3-147">Gender = (значения являются одним из административных пола)</span><span class="sxs-lookup"><span data-stu-id="690d3-147">gender=(values being one of the administrative-gender)</span></span>
 - <span data-ttu-id="690d3-148">\_Count (максимальное количество возвращаемых результатов)</span><span class="sxs-lookup"><span data-stu-id="690d3-148">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="690d3-149">Ответ должен содержать общее количество записей, возвращенных в результате поиска, и \_ счетчик будет использоваться PatientsApp, чтобы ограничить количество возвращаемых записей.</span><span class="sxs-lookup"><span data-stu-id="690d3-149">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="690d3-150">Идентификатор =\<mrn></span><span class="sxs-lookup"><span data-stu-id="690d3-150">identifier=\<mrn></span></span>

<span data-ttu-id="690d3-151">Цель — найти и отфильтровать пациента в пациент, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="690d3-151">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="690d3-152">ID: это идентификатор ресурса, который содержит каждый ресурс в FHIR.</span><span class="sxs-lookup"><span data-stu-id="690d3-152">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="690d3-153">MRN: фактический идентификатор пациента, который будет знать Clinical сотрудника.</span><span class="sxs-lookup"><span data-stu-id="690d3-153">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="690d3-154">Мы понимаем, что этот MRN основывается на типе идентификатора в ресурсе идентификатора в FHIR.</span><span class="sxs-lookup"><span data-stu-id="690d3-154">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="690d3-155">Имя</span><span class="sxs-lookup"><span data-stu-id="690d3-155">Name</span></span>
- <span data-ttu-id="690d3-156">Рождения</span><span class="sxs-lookup"><span data-stu-id="690d3-156">Birthdate</span></span>

<span data-ttu-id="690d3-157">Посмотрите следующий пример звонка:</span><span class="sxs-lookup"><span data-stu-id="690d3-157">See the following example of the call:</span></span>

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

<span data-ttu-id="690d3-158">[https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="690d3-158">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="690d3-159">Наблюдение</span><span class="sxs-lookup"><span data-stu-id="690d3-159">Observation</span></span>

<span data-ttu-id="690d3-160">Это минимальные обязательные поля, которые являются подмножеством [профиля Argonaut Vital-Signs](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span><span class="sxs-lookup"><span data-stu-id="690d3-160">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

 - <span data-ttu-id="690d3-161">Эффективная (Дата и время)</span><span class="sxs-lookup"><span data-stu-id="690d3-161">Effective (date time or period)</span></span>
 - <span data-ttu-id="690d3-162">Код. кодирование. Code</span><span class="sxs-lookup"><span data-stu-id="690d3-162">Code.Coding.Code</span></span>
 - <span data-ttu-id="690d3-163">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="690d3-163">ValueQuantity.Value</span></span>

<span data-ttu-id="690d3-164">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="690d3-164">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="690d3-165">Код. программирование. Display</span><span class="sxs-lookup"><span data-stu-id="690d3-165">Code.Coding.Display</span></span>
 - <span data-ttu-id="690d3-166">ValueQuantity. ед.</span><span class="sxs-lookup"><span data-stu-id="690d3-166">ValueQuantity.Unit</span></span>

<span data-ttu-id="690d3-167">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="690d3-167">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="690d3-168">пациент =\<patient id></span><span class="sxs-lookup"><span data-stu-id="690d3-168">patient=\<patient id></span></span>
 - <span data-ttu-id="690d3-169">_sort =-Дата</span><span class="sxs-lookup"><span data-stu-id="690d3-169">_sort=-date</span></span>
 - <span data-ttu-id="690d3-170">Category (мы будем запрашивать "Category =", чтобы получить список важных знаков.</span><span class="sxs-lookup"><span data-stu-id="690d3-170">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="690d3-171">Ниже приведен пример звонка.</span><span class="sxs-lookup"><span data-stu-id="690d3-171">Refer to this example of the call:</span></span>

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

<span data-ttu-id="690d3-172">[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="690d3-172">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="690d3-173">Условие</span><span class="sxs-lookup"><span data-stu-id="690d3-173">Condition</span></span>

<span data-ttu-id="690d3-174">Ниже приведено минимально необходимое поле, которое является подмножеством [профиля условия Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span><span class="sxs-lookup"><span data-stu-id="690d3-174">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

 - <span data-ttu-id="690d3-175">Код. кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="690d3-175">Code.Coding[0].Display</span></span>

<span data-ttu-id="690d3-176">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="690d3-176">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="690d3-177">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="690d3-177">AssertedDate</span></span>
 - <span data-ttu-id="690d3-178">Уровню серьезности</span><span class="sxs-lookup"><span data-stu-id="690d3-178">Severity</span></span>

<span data-ttu-id="690d3-179">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="690d3-179">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="690d3-180">пациент =\<patient id></span><span class="sxs-lookup"><span data-stu-id="690d3-180">patient=\<patient id></span></span>
 - <span data-ttu-id="690d3-181">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="690d3-181">_count=\<max results></span></span>

<span data-ttu-id="690d3-182">Ниже приведен пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="690d3-182">See the following example of this call:</span></span>

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

<span data-ttu-id="690d3-183">[https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="690d3-183">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="690d3-184">Происходит</span><span class="sxs-lookup"><span data-stu-id="690d3-184">Encounter</span></span>

<span data-ttu-id="690d3-185">Это минимальные обязательные поля, которые являются подмножеством подмножества [основного профиля](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) , которое должно иметь "поля".</span><span class="sxs-lookup"><span data-stu-id="690d3-185">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

 - <span data-ttu-id="690d3-186">Состояни</span><span class="sxs-lookup"><span data-stu-id="690d3-186">Status</span></span>
 - <span data-ttu-id="690d3-187">Введите [0]. Кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="690d3-187">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="690d3-188">Кроме того, ниже перечислены поля, которые можно получить из основных полей "требуется поддержка" для профиля в США.</span><span class="sxs-lookup"><span data-stu-id="690d3-188">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

 - <span data-ttu-id="690d3-189">Period. Start</span><span class="sxs-lookup"><span data-stu-id="690d3-189">Period.Start</span></span>
 - <span data-ttu-id="690d3-190">Расположение [0]. Расположение. Display</span><span class="sxs-lookup"><span data-stu-id="690d3-190">Location[0].Location.Display</span></span>

<span data-ttu-id="690d3-191">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="690d3-191">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="690d3-192">пациент =\<patient id></span><span class="sxs-lookup"><span data-stu-id="690d3-192">patient=\<patient id></span></span>
 - <span data-ttu-id="690d3-193">_sort: DESC =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="690d3-193">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="690d3-194">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="690d3-194">_count=\<max results></span></span>

<span data-ttu-id="690d3-195">Цель — получить Последнее известное расположение пациента.</span><span class="sxs-lookup"><span data-stu-id="690d3-195">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="690d3-196">Каждый из этих обнаружений ссылается на ресурс расположения.</span><span class="sxs-lookup"><span data-stu-id="690d3-196">Each encounter references a location resource.</span></span> <span data-ttu-id="690d3-197">Ссылка также должна включать поле отображения местоположения.</span><span class="sxs-lookup"><span data-stu-id="690d3-197">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="690d3-198">[https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="690d3-198">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="690d3-199">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="690d3-199">AllergyIntolerance</span></span>

<span data-ttu-id="690d3-200">Это минимальные обязательные поля, которые являются подмножеством профиля [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :</span><span class="sxs-lookup"><span data-stu-id="690d3-200">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

 - <span data-ttu-id="690d3-201">Code. Text</span><span class="sxs-lookup"><span data-stu-id="690d3-201">Code.Text</span></span>
 - <span data-ttu-id="690d3-202">Код. кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="690d3-202">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="690d3-203">ClinicalStatus/VerificationStatus (мы прочитали оба)</span><span class="sxs-lookup"><span data-stu-id="690d3-203">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="690d3-204">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также может прочитать следующее поле:</span><span class="sxs-lookup"><span data-stu-id="690d3-204">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

 - <span data-ttu-id="690d3-205">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="690d3-205">AssertedDate</span></span>
 - <span data-ttu-id="690d3-206">Примечание. текст</span><span class="sxs-lookup"><span data-stu-id="690d3-206">Note.Text</span></span>
 - <span data-ttu-id="690d3-207">Реакция</span><span class="sxs-lookup"><span data-stu-id="690d3-207">Reaction</span></span>
    - <span data-ttu-id="690d3-208">Вещество (один элемент кодирования)</span><span class="sxs-lookup"><span data-stu-id="690d3-208">Substance (one coding element)</span></span>
    - <span data-ttu-id="690d3-209">Манифест (один элемент кодирования)</span><span class="sxs-lookup"><span data-stu-id="690d3-209">Manifestation (one coding element)</span></span>

<span data-ttu-id="690d3-210">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="690d3-210">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="690d3-211">Пациент =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="690d3-211">Patient =  \<patient id></span></span>

<span data-ttu-id="690d3-212">Посмотрите следующий пример звонка:</span><span class="sxs-lookup"><span data-stu-id="690d3-212">See the following example of the call:</span></span> 

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

<span data-ttu-id="690d3-213">[https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="690d3-213">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="690d3-214">Запрос лечения</span><span class="sxs-lookup"><span data-stu-id="690d3-214">Medication Request</span></span>

<span data-ttu-id="690d3-215">Ниже указаны минимальные обязательные поля, которые являются подмножеством [профиля запроса "основной лечения" США](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html).</span><span class="sxs-lookup"><span data-stu-id="690d3-215">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

 - <span data-ttu-id="690d3-216">Лечения. Display (если ссылка)</span><span class="sxs-lookup"><span data-stu-id="690d3-216">Medication.Display (if Reference)</span></span>
 - <span data-ttu-id="690d3-217">Лечения. Text (если CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="690d3-217">Medication.Text (if CodableConcept)</span></span>
 - <span data-ttu-id="690d3-218">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="690d3-218">AuthoredOn</span></span>
 - <span data-ttu-id="690d3-219">Запросивший. агент. Display</span><span class="sxs-lookup"><span data-stu-id="690d3-219">Requester.Agent.Display</span></span>

<span data-ttu-id="690d3-220">В дополнение к полям "основные" в США для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="690d3-220">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="690d3-221">DosageInstruction[..]. Текстовые</span><span class="sxs-lookup"><span data-stu-id="690d3-221">DosageInstruction[..].Text</span></span>
 - <span data-ttu-id="690d3-222">Текстовые</span><span class="sxs-lookup"><span data-stu-id="690d3-222">Text</span></span>

<span data-ttu-id="690d3-223">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="690d3-223">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="690d3-224">пациент =\<patient id></span><span class="sxs-lookup"><span data-stu-id="690d3-224">patient=\<patient id></span></span>
 - <span data-ttu-id="690d3-225">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="690d3-225">_count=\<max results></span></span>

<span data-ttu-id="690d3-226">[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="690d3-226">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="690d3-227">Приложения</span><span class="sxs-lookup"><span data-stu-id="690d3-227">Coverage</span></span>

<span data-ttu-id="690d3-228">Это минимальный обязательный набор полей, не охваченных профилями США или Argonaut:</span><span class="sxs-lookup"><span data-stu-id="690d3-228">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="690d3-229">Группировка, по крайней мере один элемент с</span><span class="sxs-lookup"><span data-stu-id="690d3-229">Grouping, at least one element with</span></span>
    - <span data-ttu-id="690d3-230">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="690d3-230">GroupDisplay</span></span>
    - <span data-ttu-id="690d3-231">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="690d3-231">PlanDisplay</span></span>
 - <span data-ttu-id="690d3-232">Срока</span><span class="sxs-lookup"><span data-stu-id="690d3-232">Period</span></span>
 - <span data-ttu-id="690d3-233">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="690d3-233">SubscriberId</span></span>

<span data-ttu-id="690d3-234">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="690d3-234">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="690d3-235">Пациент = \<patient id></span><span class="sxs-lookup"><span data-stu-id="690d3-235">Patient = \<patient id></span></span>

<span data-ttu-id="690d3-236">[https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="690d3-236">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
