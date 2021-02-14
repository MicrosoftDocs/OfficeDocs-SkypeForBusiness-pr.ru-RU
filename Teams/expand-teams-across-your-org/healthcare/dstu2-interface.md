---
title: Интерфейс интеграции приложения "Пациенты" и EHR с DSTU2
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
description: Узнайте о спецификации интерфейса DSTU2 в Teams, в том числе о настройке или перенастройке сервера FHIR для работы с приложением "Пациенты" Microsoft Teams.
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 12833ea55977cf7e8d18ee5c10b1f17d898b27b3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803487"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="4927e-103">Характеристики интерфейса DSTU2</span><span class="sxs-lookup"><span data-stu-id="4927e-103">DSTU2 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="4927e-104">С 30 октября 2020 г. приложение "Пациенты" было отменено и заменено приложением ["Списки"](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) в Teams.</span><span class="sxs-lookup"><span data-stu-id="4927e-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="4927e-105">Данные приложения "Пациенты" хранятся в почтовом ящике группы Office 365, которая сохраняет данные команды.</span><span class="sxs-lookup"><span data-stu-id="4927e-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="4927e-106">Все данные, связанные с приложением "Пациенты", сохраняются в этой группе, но к ним нельзя получить доступ через пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="4927e-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="4927e-107">Пользователи могут создавать списки повторно с помощью приложения ["Списки".](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)</span><span class="sxs-lookup"><span data-stu-id="4927e-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="4927e-108">С помощью списков группы обслуживания в вашей организации здравоохранения могут создавать списки пациентов для сценариев, которые могут быть: от округов и межпрофиленных собраний до общего наблюдения пациентов.</span><span class="sxs-lookup"><span data-stu-id="4927e-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="4927e-109">Чтобы начать, ознакомьтесь с шаблоном "Пациенты" в списке.</span><span class="sxs-lookup"><span data-stu-id="4927e-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="4927e-110">Дополнительные информацию об управлении приложением "Списки" в организации см. в приложении ["Управление списками".](../../manage-lists-app.md)</span><span class="sxs-lookup"><span data-stu-id="4927e-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="4927e-111">Для настройки или перенастройки сервера FHIR для работы с приложением "Пациенты" в Microsoft Teams необходимо понимать, какие данные необходимы приложению для доступа.</span><span class="sxs-lookup"><span data-stu-id="4927e-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="4927e-112">Сервер FHIR должен поддерживать запросы POST с помощью пакетов для следующих ресурсов:</span><span class="sxs-lookup"><span data-stu-id="4927e-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="4927e-113">Пациент</span><span class="sxs-lookup"><span data-stu-id="4927e-113">Patient</span></span>](#patient)
- [<span data-ttu-id="4927e-114">Наблюдение</span><span class="sxs-lookup"><span data-stu-id="4927e-114">Observation</span></span>](#observation)
- [<span data-ttu-id="4927e-115">Условие</span><span class="sxs-lookup"><span data-stu-id="4927e-115">Condition</span></span>](#condition)
- [<span data-ttu-id="4927e-116">Встреча</span><span class="sxs-lookup"><span data-stu-id="4927e-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="4927e-117">Заковывная скайп</span><span class="sxs-lookup"><span data-stu-id="4927e-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="4927e-118">Покрытие</span><span class="sxs-lookup"><span data-stu-id="4927e-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="4927e-119">Medication Order</span><span class="sxs-lookup"><span data-stu-id="4927e-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="4927e-120">Расположение</span><span class="sxs-lookup"><span data-stu-id="4927e-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="4927e-121">Ресурс "Пациент" — это единственный обязательный ресурс (без которого приложение не будет загружаться).</span><span class="sxs-lookup"><span data-stu-id="4927e-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="4927e-122">Однако партнеру рекомендуется реализовать поддержку для всех указанных выше ресурсов в соответствии с указанными ниже спецификациями, чтобы лучше всего работать с приложением "Пациенты" в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4927e-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="4927e-123">Запросы из приложения "Пациенты" Microsoft Teams для более чем одного ресурса разоотмешяют пакеты (BATCH) запросов по URL-адресу сервера FHIR.</span><span class="sxs-lookup"><span data-stu-id="4927e-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="4927e-124">Сервер обрабатывает каждый запрос и возвращает пакет ресурсов, которые соответствуют каждому запросу.</span><span class="sxs-lookup"><span data-stu-id="4927e-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="4927e-125">Дополнительные сведения и примеры см. в [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="4927e-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="4927e-126">Все следующие ресурсы FHIR должны быть доступны по прямой ссылке на них.</span><span class="sxs-lookup"><span data-stu-id="4927e-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="4927e-127">Набор полей соответствия</span><span class="sxs-lookup"><span data-stu-id="4927e-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="4927e-128">Чтобы мы реализовали заявление о соответствии для FHIR Server, мы должны получить сводку о его возможностях.</span><span class="sxs-lookup"><span data-stu-id="4927e-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="4927e-129">На FHIR-сервере DSTU2 мы ожидаем, что ниже заданы параметры:</span><span class="sxs-lookup"><span data-stu-id="4927e-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="4927e-130">REST</span><span class="sxs-lookup"><span data-stu-id="4927e-130">REST</span></span>

    - <span data-ttu-id="4927e-131">Режим</span><span class="sxs-lookup"><span data-stu-id="4927e-131">Mode</span></span>
    - <span data-ttu-id="4927e-132">Взаимодействие</span><span class="sxs-lookup"><span data-stu-id="4927e-132">Interaction</span></span>
    - <span data-ttu-id="4927e-133">Ресурс: тип</span><span class="sxs-lookup"><span data-stu-id="4927e-133">Resource: Type</span></span>
    - <span data-ttu-id="4927e-134">Безопасность: [расширение для URIs OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="4927e-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="4927e-135">FhirVersion (В нашем коде это необходимо для того, чтобы понять, какую версию следует сархить, так как поддерживается несколько версий.)</span><span class="sxs-lookup"><span data-stu-id="4927e-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="4927e-136">Другие [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) сведения об этом наборе полей см. в этой области.</span><span class="sxs-lookup"><span data-stu-id="4927e-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="4927e-137">Пациент</span><span class="sxs-lookup"><span data-stu-id="4927e-137">Patient</span></span>

<span data-ttu-id="4927e-138">Они являются полями, которые являются подмножество полей профиля пациентов "Аргонаут": [](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)</span><span class="sxs-lookup"><span data-stu-id="4927e-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="4927e-139">Name.Family</span><span class="sxs-lookup"><span data-stu-id="4927e-139">Name.Family</span></span>
 - <span data-ttu-id="4927e-140">Name.Given</span><span class="sxs-lookup"><span data-stu-id="4927e-140">Name.Given</span></span>
 - <span data-ttu-id="4927e-141">Пол</span><span class="sxs-lookup"><span data-stu-id="4927e-141">Gender</span></span>
 - <span data-ttu-id="4927e-142">BirthDate</span><span class="sxs-lookup"><span data-stu-id="4927e-142">BirthDate</span></span>
 - <span data-ttu-id="4927e-143">MRN (Идентификатор)</span><span class="sxs-lookup"><span data-stu-id="4927e-143">MRN (Identifier)</span></span>

<span data-ttu-id="4927e-144">Помимо полей "Аргонаут", приложение "Пациенты" также может читать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="4927e-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="4927e-145">Name.Use</span><span class="sxs-lookup"><span data-stu-id="4927e-145">Name.Use</span></span>
 - <span data-ttu-id="4927e-146">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="4927e-146">Name.Prefix</span></span>
 - <span data-ttu-id="4927e-147">CareProvider (Ссылка на ресурс "Пациент" должна включать отображаемые поля, показанные в следующем примере).)</span><span class="sxs-lookup"><span data-stu-id="4927e-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

    ```
    Request:
    GET <fhir-server>/Patient/<patient-id>
    
    Response:
    {
      "resourceType": "Patient",
      "id": "<patient-id>",
      .
      .
      .
      "name": [
        {
          "use": "official",
          "prefix": [ "Mr" ],
          "family": [ "Chau" ],
          "given": [ "Hugh" ]
        }
      ],
      "identifier": [
        {
          "use": "official",
          "type": {
            "coding": [
              {
                "system": "https://hl7.org/fhir/v2/0203",
                "code": "MR"
              }
            ]
          },
          "value": "1234567"
        }
      ],
      "gender": "male",
      "birthDate": "1957-06-05",
      "careProvider": [{ "display": "Jane Doe" }],
    }
    ```

<span data-ttu-id="4927e-148">При поиске ресурсов метод POST используется для параметра /Patient/_search и следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="4927e-148">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="4927e-149">id</span><span class="sxs-lookup"><span data-stu-id="4927e-149">id</span></span>
 - <span data-ttu-id="4927e-150">family:contains=(ищет всех пациентов, имя которых содержит значение.)</span><span class="sxs-lookup"><span data-stu-id="4927e-150">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="4927e-151">given=\<substring></span><span class="sxs-lookup"><span data-stu-id="4927e-151">given=\<substring></span></span>
 - <span data-ttu-id="4927e-152">name=\<substring></span><span class="sxs-lookup"><span data-stu-id="4927e-152">name=\<substring></span></span>
 - <span data-ttu-id="4927e-153">birthdate=(exact match)</span><span class="sxs-lookup"><span data-stu-id="4927e-153">birthdate=(exact match)</span></span>
 - <span data-ttu-id="4927e-154">\_count (максимальное количество возвращаемых результатов)</span><span class="sxs-lookup"><span data-stu-id="4927e-154">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="4927e-155">Ответ должен содержать общее количество записей, возвращенных в результате поиска, и будет использоваться регистратором "Пациенты" для ограничения числа \_ возвращаемой записи.</span><span class="sxs-lookup"><span data-stu-id="4927e-155">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="4927e-156">идентификатор=\<mrn></span><span class="sxs-lookup"><span data-stu-id="4927e-156">identifier=\<mrn></span></span>

<span data-ttu-id="4927e-157">Цель состоит в том, чтобы иметь возможность поиска и фильтрации для пациента следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4927e-157">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="4927e-158">ИД: это ИД ресурса, который есть у каждого ресурса в FHIR.</span><span class="sxs-lookup"><span data-stu-id="4927e-158">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="4927e-159">MRN: это фактический идентификатор пациента, который будет знать пациент.</span><span class="sxs-lookup"><span data-stu-id="4927e-159">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="4927e-160">Мы понимаем, что эта MRN основана на типе идентификатора в идентификаторе ресурса в FHIR</span><span class="sxs-lookup"><span data-stu-id="4927e-160">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="4927e-161">Имя</span><span class="sxs-lookup"><span data-stu-id="4927e-161">Name</span></span>
- <span data-ttu-id="4927e-162">Birthdate</span><span class="sxs-lookup"><span data-stu-id="4927e-162">Birthdate</span></span>

<span data-ttu-id="4927e-163">См. пример этого звонка.</span><span class="sxs-lookup"><span data-stu-id="4927e-163">See the following example  of this call.</span></span>

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=hugh&family=chau

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  .
  .
  .
  "entry": [
    {
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "name": [
          {
            "text": "Hugh Chau",
            "family": [ "Chau" ],
            "given": [ "Hugh" ]
          }
        ],
        "gender": "male",
        "birthDate": "1957-06-05"
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

<span data-ttu-id="4927e-164">Другие [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) сведения об этом наборе полей см. в этой области.</span><span class="sxs-lookup"><span data-stu-id="4927e-164">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="4927e-165">Наблюдение</span><span class="sxs-lookup"><span data-stu-id="4927e-165">Observation</span></span>

<span data-ttu-id="4927e-166">Они являются полями, которые являются частью профиля важных знаков Argonaut:</span><span class="sxs-lookup"><span data-stu-id="4927e-166">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="4927e-167">Эффективные (дата или период)</span><span class="sxs-lookup"><span data-stu-id="4927e-167">Effective (date time or period)</span></span>
 - <span data-ttu-id="4927e-168">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="4927e-168">Code.Coding.Code</span></span>
 - <span data-ttu-id="4927e-169">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="4927e-169">ValueQuantity.Value</span></span>

<span data-ttu-id="4927e-170">Помимо полей "Аргонаут", приложение "Пациенты" также может читать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="4927e-170">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="4927e-171">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="4927e-171">Code.Coding.Display</span></span>
 - <span data-ttu-id="4927e-172">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="4927e-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="4927e-173">При использовании наблюдений компонентов та же логика применяется для каждого наблюдения компонентов.</span><span class="sxs-lookup"><span data-stu-id="4927e-173">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="4927e-174">При поиске ресурсов используются метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="4927e-174">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="4927e-175">patient=\<patient id\></span><span class="sxs-lookup"><span data-stu-id="4927e-175">patient=\<patient id\></span></span>
 - <span data-ttu-id="4927e-176">sort:desc=\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="4927e-176">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="4927e-177">Цель — получить последние жизненно важные знаки для пациента [VitalSigns.DSTU.saz] (наблюдение?).</span><span class="sxs-lookup"><span data-stu-id="4927e-177">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs

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
        "category": {
          "coding": [ { code": "vital-signs" } ],
        },
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "39156-5",
              "display": "bmi"
            }
          ],
        },
        "effectiveDateTime": "2009-12-01",
        "valueQuantity": {
          "value": 34.4,
          "unit": "kg/m2",
          "system": "http://unitsofmeasure.org",
          "code": "kg/m2"
        }
      },
    },
    .
    .
    .
  ]
}
```

<span data-ttu-id="4927e-178">Другие [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) сведения об этом наборе полей см. в этой области.</span><span class="sxs-lookup"><span data-stu-id="4927e-178">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="4927e-179">Условие</span><span class="sxs-lookup"><span data-stu-id="4927e-179">Condition</span></span>

<span data-ttu-id="4927e-180">Это минимальные необходимые поля, которые являются подмножество профиля условия [Argonaut:](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)</span><span class="sxs-lookup"><span data-stu-id="4927e-180">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="4927e-181">Code.Coding[0]. Экран</span><span class="sxs-lookup"><span data-stu-id="4927e-181">Code.Coding[0].Display</span></span>

<span data-ttu-id="4927e-182">Помимо полей "Аргонаут", приложение "Пациенты" также может читать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="4927e-182">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="4927e-183">Дата записи</span><span class="sxs-lookup"><span data-stu-id="4927e-183">Date Recorded</span></span>
 - <span data-ttu-id="4927e-184">Серьезность</span><span class="sxs-lookup"><span data-stu-id="4927e-184">Severity</span></span>

<span data-ttu-id="4927e-185">При поиске ресурсов используются метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="4927e-185">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="4927e-186">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="4927e-186">patient=\<patient id></span></span>
 - <span data-ttu-id="4927e-187">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="4927e-187">_count=\<max results></span></span>

<span data-ttu-id="4927e-188">См. пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="4927e-188">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/Condition?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "386033004",
              "display": "Neuropathy (nerve damage)"
            }
          ]
        },
        "dateRecorded": "2018-09-17",
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        }
      },
    }
  ]
}
```

<span data-ttu-id="4927e-189">Другие [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) сведения об этом наборе полей см. в этой области.</span><span class="sxs-lookup"><span data-stu-id="4927e-189">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="4927e-190">Встреча</span><span class="sxs-lookup"><span data-stu-id="4927e-190">Encounter</span></span>

<span data-ttu-id="4927e-191">Это минимальные необходимые поля, которые являются подмножеством полей профиля Core Encounter в США:</span><span class="sxs-lookup"><span data-stu-id="4927e-191">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="4927e-192">Состояние</span><span class="sxs-lookup"><span data-stu-id="4927e-192">Status</span></span>
 - <span data-ttu-id="4927e-193">Введите[0]. Coding[0]. Экран</span><span class="sxs-lookup"><span data-stu-id="4927e-193">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="4927e-194">Кроме того, следующие поля из профилей US Core Encounter "необходимо поддерживать"</span><span class="sxs-lookup"><span data-stu-id="4927e-194">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="4927e-195">Period.Start</span><span class="sxs-lookup"><span data-stu-id="4927e-195">Period.Start</span></span>
 - <span data-ttu-id="4927e-196">Location[0]. Location.Display</span><span class="sxs-lookup"><span data-stu-id="4927e-196">Location[0].Location.Display</span></span>

<span data-ttu-id="4927e-197">При поиске ресурсов используются метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="4927e-197">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="4927e-198">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="4927e-198">patient=\<patient id></span></span>
 - <span data-ttu-id="4927e-199">_sort:desc=\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="4927e-199">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="4927e-200">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="4927e-200">_count=\<max results></span></span>

<span data-ttu-id="4927e-201">Цель — получить последнее известное местоположение пациента.</span><span class="sxs-lookup"><span data-stu-id="4927e-201">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="4927e-202">Каждое из этих встреч ссылается на ресурс расположения.</span><span class="sxs-lookup"><span data-stu-id="4927e-202">Each encounter references a location resource.</span></span> <span data-ttu-id="4927e-203">В ссылку также должно быть включено отображаемого поля расположения.</span><span class="sxs-lookup"><span data-stu-id="4927e-203">The reference shall also include the location's display field.</span></span> <span data-ttu-id="4927e-204">См. пример этого звонка.</span><span class="sxs-lookup"><span data-stu-id="4927e-204">See the following example of this call.</span></span>

```
Request:
GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Encounter",
        "id": "<resource-id>",
        "identifier": [{ "use": "official", "value": "<id>" }],
        "status": "arrived",
        "type": [
          {
            "coding": [{ "display": "Appointment" }],
          }
        ],
        "patient": { "reference": "Patient/<patient-id>" },
        "period": { "start": "09/17/2018 1:00:00 PM" },
        "location": [
          {
            "location": { "display": "Clinic - ENT" },
          }
        ]
      }
    }
  ]
}
```

<span data-ttu-id="4927e-205">Другие [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) сведения об этом наборе полей см. в этой области.</span><span class="sxs-lookup"><span data-stu-id="4927e-205">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="4927e-206">Окномерации</span><span class="sxs-lookup"><span data-stu-id="4927e-206">AllergyIntolerance</span></span>

<span data-ttu-id="4927e-207">Они являются полями, которые являются подмножество профиля Argonaut ВячестьIntolerance:</span><span class="sxs-lookup"><span data-stu-id="4927e-207">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="4927e-208">Code.Text</span><span class="sxs-lookup"><span data-stu-id="4927e-208">Code.Text</span></span>
 - <span data-ttu-id="4927e-209">Code.Coding[0]. Экран</span><span class="sxs-lookup"><span data-stu-id="4927e-209">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="4927e-210">Состояние</span><span class="sxs-lookup"><span data-stu-id="4927e-210">Status</span></span>

<span data-ttu-id="4927e-211">Помимо полей "Аргонаут", приложение "Пациенты" также может читать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="4927e-211">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="4927e-212">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="4927e-212">RecordedDate</span></span>
 - <span data-ttu-id="4927e-213">Note.Text</span><span class="sxs-lookup"><span data-stu-id="4927e-213">Note.Text</span></span>
 - <span data-ttu-id="4927e-214">Реакция[..]. Вааля.Текст</span><span class="sxs-lookup"><span data-stu-id="4927e-214">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="4927e-215">Реакция[..]. Заме же[..]. Текст</span><span class="sxs-lookup"><span data-stu-id="4927e-215">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="4927e-216">Text.Div</span><span class="sxs-lookup"><span data-stu-id="4927e-216">Text.Div</span></span>

<span data-ttu-id="4927e-217">При поиске ресурсов используются метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="4927e-217">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="4927e-218">Patient =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="4927e-218">Patient =  \<patient id></span></span>

<span data-ttu-id="4927e-219">См. пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="4927e-219">See the following example of this call:</span></span>

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
        "recordedDate": "2018-09-17T07:00:00.000Z",
        "substance": {
          "text": "Cashew nuts"
        },
        "status": "confirmed",
        "reaction": [
          {
            "substance": {
              "text": "cashew nut allergenic extract Injectable Product"
            },
            "manifestation": [
              {
                "text": "Anaphylactic reaction"
              }
            ]
          }
        ]
      }
    }
  ]
}
```

<span data-ttu-id="4927e-220">Другие [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) сведения об этом наборе полей см. в этой области.</span><span class="sxs-lookup"><span data-stu-id="4927e-220">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="4927e-221">Medication Order</span><span class="sxs-lookup"><span data-stu-id="4927e-221">Medication Order</span></span>

<span data-ttu-id="4927e-222">Они требуются для полей, которые являются частью профиля Argonaut Висячегов:</span><span class="sxs-lookup"><span data-stu-id="4927e-222">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="4927e-223">DateWritten</span><span class="sxs-lookup"><span data-stu-id="4927e-223">DateWritten</span></span>
 - <span data-ttu-id="4927e-224">Висяк.Дисплей</span><span class="sxs-lookup"><span data-stu-id="4927e-224">Prescriber.Display</span></span>
 - <span data-ttu-id="4927e-225">Неявная.Дисплей (если ссылка)</span><span class="sxs-lookup"><span data-stu-id="4927e-225">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="4927e-226">Висяк.Текст (если концепция)</span><span class="sxs-lookup"><span data-stu-id="4927e-226">Medication.Text (if concept)</span></span>

<span data-ttu-id="4927e-227">Помимо полей "Аргонаут", приложение "Пациенты" также может читать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="4927e-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="4927e-228">DateEnded</span><span class="sxs-lookup"><span data-stu-id="4927e-228">DateEnded</span></span>
 - <span data-ttu-id="4927e-229">Instruction.Text</span><span class="sxs-lookup"><span data-stu-id="4927e-229">DosageInstruction.Text</span></span>
 - <span data-ttu-id="4927e-230">Text.Div</span><span class="sxs-lookup"><span data-stu-id="4927e-230">Text.Div</span></span>

<span data-ttu-id="4927e-231">При поиске ресурсов используются метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="4927e-231">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="4927e-232">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="4927e-232">patient=\<patient id></span></span>
 - <span data-ttu-id="4927e-233">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="4927e-233">_count=\<max results></span></span>

<span data-ttu-id="4927e-234">См. пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="4927e-234">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "MedicationOrder",
        "id": "<resource-id>",
        "dateWritten": "2018-09-17",
        "medicationCodeableConcept": {
          "text": "Lisinopril 20 MG Oral Tablet"
        },
        "prescriber": {
          "display": "Jane Doe"
        },
        "dosageInstruction": [
          {
            "text": "1 daily"
          }
        ]
      }
    }
  ]
}
```

<span data-ttu-id="4927e-235">Другие [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) сведения об этом наборе полей см. в этой области.</span><span class="sxs-lookup"><span data-stu-id="4927e-235">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="4927e-236">Покрытие</span><span class="sxs-lookup"><span data-stu-id="4927e-236">Coverage</span></span>

<span data-ttu-id="4927e-237">Они требуются для полей, которые не охватываются профилями US Core или Argonaut.</span><span class="sxs-lookup"><span data-stu-id="4927e-237">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="4927e-238">Payor</span><span class="sxs-lookup"><span data-stu-id="4927e-238">Payor</span></span>

<span data-ttu-id="4927e-239">При поиске ресурсов используются метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="4927e-239">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="4927e-240">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="4927e-240">patient=\<patient id></span></span>

<span data-ttu-id="4927e-241">См. пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="4927e-241">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/Coverage?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Coverage",
        "id": "<resource-id>",
        "plan": "No Primary Insurance",
        "subscriber": { "reference": "Patient/<patient-id>" }
      }
    }
  ]
}
```
    
<span data-ttu-id="4927e-242">Другие [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) сведения об этом наборе полей см. в этой области.</span><span class="sxs-lookup"><span data-stu-id="4927e-242">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="4927e-243">Местоположение</span><span class="sxs-lookup"><span data-stu-id="4927e-243">Location</span></span>

<span data-ttu-id="4927e-244">Этот ресурс используется только в качестве ссылки на ресурс [Encounter.](#encounter)</span><span class="sxs-lookup"><span data-stu-id="4927e-244">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="4927e-245">Другие [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) сведения об этом наборе полей см. в этой области.</span><span class="sxs-lookup"><span data-stu-id="4927e-245">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
