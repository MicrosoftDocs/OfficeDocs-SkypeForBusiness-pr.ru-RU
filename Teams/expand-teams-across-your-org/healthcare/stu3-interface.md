---
title: Интерфейс STU3 интеграции приложения "Пациенты" и EHR
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
description: Узнайте, как интегрировать электронные медицинские записи в приложение "Пациенты" Microsoft Teams и спецификацию интерфейса STU3.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e20619badb2509d0a90f396563a98796e718e2f
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803497"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="264cc-103">Характеристики интерфейса STU3</span><span class="sxs-lookup"><span data-stu-id="264cc-103">STU3 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="264cc-104">С 30 октября 2020 г. приложение "Пациенты" [](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) было отменено и заменено приложением "Списки" в Teams.</span><span class="sxs-lookup"><span data-stu-id="264cc-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="264cc-105">Данные приложения "Пациенты" хранятся в почтовом ящике группы Office 365, которая сохраняет данные команды.</span><span class="sxs-lookup"><span data-stu-id="264cc-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="264cc-106">Все данные, связанные с приложением "Пациенты", сохраняются в этой группе, но к ним нельзя получить доступ через пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="264cc-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="264cc-107">Пользователи могут создавать списки повторно с помощью приложения ["Списки".](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)</span><span class="sxs-lookup"><span data-stu-id="264cc-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="264cc-108">С помощью списков группы обслуживания в вашей организации здравоохранения могут создавать списки пациентов для сценариев, которые могут быть: от округов и межпрофиленных собраний до общего наблюдения пациентов.</span><span class="sxs-lookup"><span data-stu-id="264cc-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="264cc-109">Чтобы начать, ознакомьтесь с шаблоном "Пациенты" в списке.</span><span class="sxs-lookup"><span data-stu-id="264cc-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="264cc-110">Дополнительные информацию об управлении приложением "Списки" в организации см. в приложении ["Управление списками".](../../manage-lists-app.md)</span><span class="sxs-lookup"><span data-stu-id="264cc-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="264cc-111">Для настройки или перенастройки сервера FHIR для работы с приложением "Пациенты" в Microsoft Teams необходимо понимать, какие данные необходимы приложению для доступа.</span><span class="sxs-lookup"><span data-stu-id="264cc-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="264cc-112">Сервер FHIR должен поддерживать запросы POST с помощью пакетов для следующих ресурсов:</span><span class="sxs-lookup"><span data-stu-id="264cc-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="264cc-113">Пациент</span><span class="sxs-lookup"><span data-stu-id="264cc-113">Patient</span></span>](#patient)
- [<span data-ttu-id="264cc-114">Наблюдение</span><span class="sxs-lookup"><span data-stu-id="264cc-114">Observation</span></span>](#observation)
- [<span data-ttu-id="264cc-115">Условие</span><span class="sxs-lookup"><span data-stu-id="264cc-115">Condition</span></span>](#condition)
- [<span data-ttu-id="264cc-116">Встреча</span><span class="sxs-lookup"><span data-stu-id="264cc-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="264cc-117">Заковырова Скайп</span><span class="sxs-lookup"><span data-stu-id="264cc-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="264cc-118">Покрытие</span><span class="sxs-lookup"><span data-stu-id="264cc-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="264cc-119">[Выписка](#medication-request) по совместим (в DSTU2-версии patientsApp)</span><span class="sxs-lookup"><span data-stu-id="264cc-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="264cc-120">Расположение (сведения, необходимые для этого ресурса, могут быть включены в encounter)</span><span class="sxs-lookup"><span data-stu-id="264cc-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="264cc-121">Ресурс "Пациент" — это единственный обязательный ресурс (без которого приложение не будет загружаться); Однако партнеру рекомендуется реализовать поддержку для всех указанных выше ресурсов в соответствии с указанными ниже спецификациями, чтобы лучше всего работать с приложением "Пациенты" в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="264cc-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="264cc-122">Запросы из приложения "Пациенты" Microsoft Teams для более чем одного ресурса должны опубликовать пакет запросов (BATCH) по URL-адресу сервера FHIR.</span><span class="sxs-lookup"><span data-stu-id="264cc-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="264cc-123">Сервер должен обработать каждый запрос и вернуть пакет ресурсов, которые соответствуют каждому запросу.</span><span class="sxs-lookup"><span data-stu-id="264cc-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="264cc-124">Дополнительные сведения и примеры см. в [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="264cc-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="264cc-125">Заявление о возможности</span><span class="sxs-lookup"><span data-stu-id="264cc-125">Capability Statement</span></span>

<span data-ttu-id="264cc-126">Это поля, которые требуются для минимального размера:</span><span class="sxs-lookup"><span data-stu-id="264cc-126">These are the minimum required fields:</span></span>

 - <span data-ttu-id="264cc-127">REST</span><span class="sxs-lookup"><span data-stu-id="264cc-127">REST</span></span>

    - <span data-ttu-id="264cc-128">Режим</span><span class="sxs-lookup"><span data-stu-id="264cc-128">Mode</span></span>
    - <span data-ttu-id="264cc-129">Взаимодействие</span><span class="sxs-lookup"><span data-stu-id="264cc-129">Interaction</span></span>
    - <span data-ttu-id="264cc-130">Ресурс: тип</span><span class="sxs-lookup"><span data-stu-id="264cc-130">Resource: Type</span></span>
    - <span data-ttu-id="264cc-131">Безопасность: [расширение для URIs OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="264cc-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
    
 - <span data-ttu-id="264cc-132">FhirVersion (этот код необходим для того, чтобы понять, какую версию следует сархить.)</span><span class="sxs-lookup"><span data-stu-id="264cc-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="264cc-133">Другие [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) сведения об этом наборе полей см. в этой области.</span><span class="sxs-lookup"><span data-stu-id="264cc-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="264cc-134">Пациент</span><span class="sxs-lookup"><span data-stu-id="264cc-134">Patient</span></span>

<span data-ttu-id="264cc-135">Вот поля, которые требуются в качестве подмножество полей профиля пациентов в Аргонауте:</span><span class="sxs-lookup"><span data-stu-id="264cc-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

 - <span data-ttu-id="264cc-136">Name.Given</span><span class="sxs-lookup"><span data-stu-id="264cc-136">Name.Given</span></span>
 - <span data-ttu-id="264cc-137">Name.Family</span><span class="sxs-lookup"><span data-stu-id="264cc-137">Name.Family</span></span>
 - <span data-ttu-id="264cc-138">Пол</span><span class="sxs-lookup"><span data-stu-id="264cc-138">Gender</span></span>
 - <span data-ttu-id="264cc-139">BirthDate</span><span class="sxs-lookup"><span data-stu-id="264cc-139">BirthDate</span></span>
 - <span data-ttu-id="264cc-140">MRN (Идентификатор)</span><span class="sxs-lookup"><span data-stu-id="264cc-140">MRN (Identifier)</span></span>

<span data-ttu-id="264cc-141">Помимо полей ["Аргонаут",](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)приложение "Пациенты" также может читать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="264cc-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="264cc-142">Name.Use</span><span class="sxs-lookup"><span data-stu-id="264cc-142">Name.Use</span></span>
 - <span data-ttu-id="264cc-143">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="264cc-143">Name.Prefix</span></span>
 - <span data-ttu-id="264cc-144">[GeneralPractitioner] — ссылка на GeneralPractitioner должна быть включена в ресурс "Пациент" (только для отображения поля).</span><span class="sxs-lookup"><span data-stu-id="264cc-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="264cc-145">При поиске ресурсов метод POST используется для параметра /Patient/_search и следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="264cc-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="264cc-146">id</span><span class="sxs-lookup"><span data-stu-id="264cc-146">id</span></span>
 - <span data-ttu-id="264cc-147">family=(ищет всех пациентов, имя которых содержит значение)</span><span class="sxs-lookup"><span data-stu-id="264cc-147">family=(searches for all patients whose family name contains the value)</span></span>
 - <span data-ttu-id="264cc-148">given=\<substring></span><span class="sxs-lookup"><span data-stu-id="264cc-148">given=\<substring></span></span>
 - <span data-ttu-id="264cc-149">birthdate=(exact match)</span><span class="sxs-lookup"><span data-stu-id="264cc-149">birthdate=(exact match)</span></span>
 - <span data-ttu-id="264cc-150">gender=(значения в административных полах)</span><span class="sxs-lookup"><span data-stu-id="264cc-150">gender=(values being one of the administrative-gender)</span></span>
 - <span data-ttu-id="264cc-151">\_count (максимальное количество возвращаемых результатов)</span><span class="sxs-lookup"><span data-stu-id="264cc-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="264cc-152">Ответ должен содержать общее количество записей, возвращенных в результате поиска, и количество будет использоваться регистратором "Пациенты" для ограничения числа \_ возвращаемой записи.</span><span class="sxs-lookup"><span data-stu-id="264cc-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="264cc-153">идентификатор=\<mrn></span><span class="sxs-lookup"><span data-stu-id="264cc-153">identifier=\<mrn></span></span>

<span data-ttu-id="264cc-154">Цель состоит в том, чтобы иметь возможность поиска и фильтрации для пациента следующим образом:</span><span class="sxs-lookup"><span data-stu-id="264cc-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="264cc-155">ИД: это ИД ресурса, который есть у каждого ресурса в FHIR.</span><span class="sxs-lookup"><span data-stu-id="264cc-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="264cc-156">MRN: это фактический идентификатор пациента, который будет знать пациент.</span><span class="sxs-lookup"><span data-stu-id="264cc-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="264cc-157">Мы понимаем, что эта MRN основана на типе идентификатора внутри ресурса идентификатора в FHIR.</span><span class="sxs-lookup"><span data-stu-id="264cc-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="264cc-158">Имя</span><span class="sxs-lookup"><span data-stu-id="264cc-158">Name</span></span>
- <span data-ttu-id="264cc-159">Birthdate</span><span class="sxs-lookup"><span data-stu-id="264cc-159">Birthdate</span></span>

<span data-ttu-id="264cc-160">См. пример звонка:</span><span class="sxs-lookup"><span data-stu-id="264cc-160">See the following example of the call:</span></span>

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

<span data-ttu-id="264cc-161">Другие [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) сведения об этом наборе полей см. в этой области.</span><span class="sxs-lookup"><span data-stu-id="264cc-161">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="264cc-162">Наблюдение</span><span class="sxs-lookup"><span data-stu-id="264cc-162">Observation</span></span>

<span data-ttu-id="264cc-163">Они являются полями, которые являются подмножество профиля [Argonaut Vital-Signs.](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)</span><span class="sxs-lookup"><span data-stu-id="264cc-163">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

 - <span data-ttu-id="264cc-164">Эффективные (дата или период)</span><span class="sxs-lookup"><span data-stu-id="264cc-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="264cc-165">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="264cc-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="264cc-166">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="264cc-166">ValueQuantity.Value</span></span>

<span data-ttu-id="264cc-167">Помимо полей "Аргонаут", приложение "Пациенты" также может читать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="264cc-167">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="264cc-168">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="264cc-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="264cc-169">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="264cc-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="264cc-170">При поиске ресурсов используются метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="264cc-170">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="264cc-171">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="264cc-171">patient=\<patient id></span></span>
 - <span data-ttu-id="264cc-172">_sort=-дата</span><span class="sxs-lookup"><span data-stu-id="264cc-172">_sort=-date</span></span>
 - <span data-ttu-id="264cc-173">(мы запросим "category=vital-signs"), чтобы получить список важных знаков.</span><span class="sxs-lookup"><span data-stu-id="264cc-173">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="264cc-174">Обратитесь к примеру звонка:</span><span class="sxs-lookup"><span data-stu-id="264cc-174">Refer to this example of the call:</span></span>

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

<span data-ttu-id="264cc-175">Другие [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) сведения об этом наборе полей см. в этой области.</span><span class="sxs-lookup"><span data-stu-id="264cc-175">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="264cc-176">Условие</span><span class="sxs-lookup"><span data-stu-id="264cc-176">Condition</span></span>

<span data-ttu-id="264cc-177">Вот минимально необходимые поля, которые являются подмножество профиля условия [Argonaut.](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)</span><span class="sxs-lookup"><span data-stu-id="264cc-177">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

 - <span data-ttu-id="264cc-178">Code.Coding[0]. Экран</span><span class="sxs-lookup"><span data-stu-id="264cc-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="264cc-179">Помимо полей "Аргонаут", приложение "Пациенты" также может читать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="264cc-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="264cc-180">ВисячийДата</span><span class="sxs-lookup"><span data-stu-id="264cc-180">AssertedDate</span></span>
 - <span data-ttu-id="264cc-181">Серьезность</span><span class="sxs-lookup"><span data-stu-id="264cc-181">Severity</span></span>

<span data-ttu-id="264cc-182">При поиске ресурсов используются метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="264cc-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="264cc-183">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="264cc-183">patient=\<patient id></span></span>
 - <span data-ttu-id="264cc-184">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="264cc-184">_count=\<max results></span></span>

<span data-ttu-id="264cc-185">См. пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="264cc-185">See the following example of this call:</span></span>

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

<span data-ttu-id="264cc-186">Другие [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) сведения об этом наборе полей см. в этой области.</span><span class="sxs-lookup"><span data-stu-id="264cc-186">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="264cc-187">Встреча</span><span class="sxs-lookup"><span data-stu-id="264cc-187">Encounter</span></span>

<span data-ttu-id="264cc-188">Это минимальные необходимые поля, которые являются подмножеством полей профиля [Core Encounter](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) в США.</span><span class="sxs-lookup"><span data-stu-id="264cc-188">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

 - <span data-ttu-id="264cc-189">Состояние</span><span class="sxs-lookup"><span data-stu-id="264cc-189">Status</span></span>
 - <span data-ttu-id="264cc-190">Введите[0]. Coding[0]. Экран</span><span class="sxs-lookup"><span data-stu-id="264cc-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="264cc-191">Кроме того, следующие поля из профилей US Core Encounter "необходимо поддерживать":</span><span class="sxs-lookup"><span data-stu-id="264cc-191">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

 - <span data-ttu-id="264cc-192">Period.Start</span><span class="sxs-lookup"><span data-stu-id="264cc-192">Period.Start</span></span>
 - <span data-ttu-id="264cc-193">Location[0]. Location.Display</span><span class="sxs-lookup"><span data-stu-id="264cc-193">Location[0].Location.Display</span></span>

<span data-ttu-id="264cc-194">При поиске ресурсов используются метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="264cc-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="264cc-195">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="264cc-195">patient=\<patient id></span></span>
 - <span data-ttu-id="264cc-196">_sort:desc=\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="264cc-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="264cc-197">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="264cc-197">_count=\<max results></span></span>

<span data-ttu-id="264cc-198">Цель — получить последнее известное местоположение пациента.</span><span class="sxs-lookup"><span data-stu-id="264cc-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="264cc-199">Каждое из этих встреч ссылается на ресурс расположения.</span><span class="sxs-lookup"><span data-stu-id="264cc-199">Each encounter references a location resource.</span></span> <span data-ttu-id="264cc-200">В ссылку также должно быть включено отображаемого поля расположения.</span><span class="sxs-lookup"><span data-stu-id="264cc-200">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="264cc-201">Другие [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) сведения об этом наборе полей см. в этой области.</span><span class="sxs-lookup"><span data-stu-id="264cc-201">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="264cc-202">Окномерации</span><span class="sxs-lookup"><span data-stu-id="264cc-202">AllergyIntolerance</span></span>

<span data-ttu-id="264cc-203">Они являются полями, которые являются подмножество профиля [Argonaut ВячестьIntolerance:](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html)</span><span class="sxs-lookup"><span data-stu-id="264cc-203">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

 - <span data-ttu-id="264cc-204">Code.Text</span><span class="sxs-lookup"><span data-stu-id="264cc-204">Code.Text</span></span>
 - <span data-ttu-id="264cc-205">Code.Coding[0]. Экран</span><span class="sxs-lookup"><span data-stu-id="264cc-205">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="264cc-206">Клиническийтаис/Проверка (мы читаем оба)</span><span class="sxs-lookup"><span data-stu-id="264cc-206">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="264cc-207">Помимо полей "Аргонаут", приложение "Пациенты" также может прочесть следующее поле:</span><span class="sxs-lookup"><span data-stu-id="264cc-207">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

 - <span data-ttu-id="264cc-208">ВисячийДата</span><span class="sxs-lookup"><span data-stu-id="264cc-208">AssertedDate</span></span>
 - <span data-ttu-id="264cc-209">Note.Text</span><span class="sxs-lookup"><span data-stu-id="264cc-209">Note.Text</span></span>
 - <span data-ttu-id="264cc-210">Реакция</span><span class="sxs-lookup"><span data-stu-id="264cc-210">Reaction</span></span>
    - <span data-ttu-id="264cc-211">Ухмайл (один элемент кода)</span><span class="sxs-lookup"><span data-stu-id="264cc-211">Substance (one coding element)</span></span>
    - <span data-ttu-id="264cc-212">Ухмыл (один элемент кода)</span><span class="sxs-lookup"><span data-stu-id="264cc-212">Manifestation (one coding element)</span></span>

<span data-ttu-id="264cc-213">При поиске ресурсов используются метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="264cc-213">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="264cc-214">Patient =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="264cc-214">Patient =  \<patient id></span></span>

<span data-ttu-id="264cc-215">См. пример звонка:</span><span class="sxs-lookup"><span data-stu-id="264cc-215">See the following example of the call:</span></span> 

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

<span data-ttu-id="264cc-216">Другие [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) сведения об этом наборе полей см. в этой области.</span><span class="sxs-lookup"><span data-stu-id="264cc-216">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="264cc-217">Запрос на прием с просьбой о прием</span><span class="sxs-lookup"><span data-stu-id="264cc-217">Medication Request</span></span>

<span data-ttu-id="264cc-218">Они являются полями, которые являются подмножество профиля основного запроса основного ядра [США:](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)</span><span class="sxs-lookup"><span data-stu-id="264cc-218">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

 - <span data-ttu-id="264cc-219">Ия.Дисплей (если ссылка)</span><span class="sxs-lookup"><span data-stu-id="264cc-219">Medication.Display (if Reference)</span></span>
 - <span data-ttu-id="264cc-220">Висячий.Текст (если CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="264cc-220">Medication.Text (if CodableConcept)</span></span>
 - <span data-ttu-id="264cc-221">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="264cc-221">AuthoredOn</span></span>
 - <span data-ttu-id="264cc-222">Requester.Agent.Display</span><span class="sxs-lookup"><span data-stu-id="264cc-222">Requester.Agent.Display</span></span>

<span data-ttu-id="264cc-223">Кроме полей "Us Core", приложение "Пациенты" может читать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="264cc-223">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="264cc-224">Instruction[..]. Текст</span><span class="sxs-lookup"><span data-stu-id="264cc-224">DosageInstruction[..].Text</span></span>
 - <span data-ttu-id="264cc-225">Текст</span><span class="sxs-lookup"><span data-stu-id="264cc-225">Text</span></span>

<span data-ttu-id="264cc-226">При поиске ресурсов используются метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="264cc-226">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="264cc-227">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="264cc-227">patient=\<patient id></span></span>
 - <span data-ttu-id="264cc-228">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="264cc-228">_count=\<max results></span></span>

<span data-ttu-id="264cc-229">Другие [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) сведения об этом наборе полей см. в этой области.</span><span class="sxs-lookup"><span data-stu-id="264cc-229">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="264cc-230">Покрытие</span><span class="sxs-lookup"><span data-stu-id="264cc-230">Coverage</span></span>

<span data-ttu-id="264cc-231">Они требуются для полей, которые не охватываются профилями US Core или Argonaut.</span><span class="sxs-lookup"><span data-stu-id="264cc-231">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="264cc-232">Группировка, по крайней мере один элемент с</span><span class="sxs-lookup"><span data-stu-id="264cc-232">Grouping, at least one element with</span></span>
    - <span data-ttu-id="264cc-233">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="264cc-233">GroupDisplay</span></span>
    - <span data-ttu-id="264cc-234">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="264cc-234">PlanDisplay</span></span>
 - <span data-ttu-id="264cc-235">Период</span><span class="sxs-lookup"><span data-stu-id="264cc-235">Period</span></span>
 - <span data-ttu-id="264cc-236">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="264cc-236">SubscriberId</span></span>

<span data-ttu-id="264cc-237">При поиске ресурсов используются метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="264cc-237">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="264cc-238">Patient = \<patient id></span><span class="sxs-lookup"><span data-stu-id="264cc-238">Patient = \<patient id></span></span>

<span data-ttu-id="264cc-239">Другие [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) сведения об этом наборе полей см. в этой области.</span><span class="sxs-lookup"><span data-stu-id="264cc-239">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
