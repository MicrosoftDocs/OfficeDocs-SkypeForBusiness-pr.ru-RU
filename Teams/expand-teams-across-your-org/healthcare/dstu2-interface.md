---
title: Интерфейс DSTU2 пациентов для приложений и EHR интеграции
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
description: Узнайте о спецификации интерфейса DSTU2 в Teams, в том числе Настройка и перенастройка сервера FHIR для работы с приложением Microsoft Teams пациентов.
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 15bcc5fcaff50d6d41c45ef2d38e34719ebca999
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772210"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="fca94-103">Характеристики интерфейса DSTU2</span><span class="sxs-lookup"><span data-stu-id="fca94-103">DSTU2 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="fca94-104">Действительно 30 октября 2020 г. приложение пациентов было прекращено и заменено [приложением "списки](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) " в Teams.</span><span class="sxs-lookup"><span data-stu-id="fca94-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="fca94-105">Благодаря спискам, благодаря вашим командам в организации здравоохранения вы сможете создавать списки пациент для сценариев, начиная с округляющих и interdisciplinaryных собраний групп и заканчивая общим мониторингом пациента.</span><span class="sxs-lookup"><span data-stu-id="fca94-105">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="fca94-106">Чтобы приступить к работе, изучите шаблон пациентов в списках.</span><span class="sxs-lookup"><span data-stu-id="fca94-106">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="fca94-107">Дополнительные сведения об управлении приложением "списки" в Организации можно найти в разделе [Управление приложением "списки"](../../manage-lists-app.md)</span><span class="sxs-lookup"><span data-stu-id="fca94-107">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md)</span></span>

<span data-ttu-id="fca94-108">Настройка или перенастройка сервера FHIR для работы с приложением Microsoft Teams пациентов требует понимания данных, к которым приложению требуется доступ.</span><span class="sxs-lookup"><span data-stu-id="fca94-108">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="fca94-109">Сервер FHIR должен поддерживать запросы POST, используя пакеты для указанных ниже ресурсов.</span><span class="sxs-lookup"><span data-stu-id="fca94-109">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="fca94-110">Подождите</span><span class="sxs-lookup"><span data-stu-id="fca94-110">Patient</span></span>](#patient)
- [<span data-ttu-id="fca94-111">Наблюдение</span><span class="sxs-lookup"><span data-stu-id="fca94-111">Observation</span></span>](#observation)
- [<span data-ttu-id="fca94-112">Условие</span><span class="sxs-lookup"><span data-stu-id="fca94-112">Condition</span></span>](#condition)
- [<span data-ttu-id="fca94-113">Происходит</span><span class="sxs-lookup"><span data-stu-id="fca94-113">Encounter</span></span>](#encounter)
- [<span data-ttu-id="fca94-114">Недопустимый Allergy</span><span class="sxs-lookup"><span data-stu-id="fca94-114">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="fca94-115">Приложения</span><span class="sxs-lookup"><span data-stu-id="fca94-115">Coverage</span></span>](#coverage)
- [<span data-ttu-id="fca94-116">Лечения заказ</span><span class="sxs-lookup"><span data-stu-id="fca94-116">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="fca94-117">Расположение</span><span class="sxs-lookup"><span data-stu-id="fca94-117">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="fca94-118">Ресурс пациент является единственным обязательным ресурсом (без которого приложение не будет загружаться вообще).</span><span class="sxs-lookup"><span data-stu-id="fca94-118">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="fca94-119">Тем не менее, рекомендуется, чтобы партнеры реализовали поддержку всех вышеупомянутых ресурсов для спецификаций, указанных ниже, для наилучшего взаимодействия с пользователем в приложении Microsoft Teams пациентов.</span><span class="sxs-lookup"><span data-stu-id="fca94-119">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="fca94-120">Запросы из приложения Microsoft Teams пациентов для нескольких ресурсов. отправляет набор (пакет) запросов на URL-адрес сервера FHIR.</span><span class="sxs-lookup"><span data-stu-id="fca94-120">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="fca94-121">Сервер обрабатывает каждый запрос и возвращает набор ресурсов, соответствующих каждому запросу.</span><span class="sxs-lookup"><span data-stu-id="fca94-121">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="fca94-122">Дополнительные сведения и примеры можно найти в разделе [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="fca94-122">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="fca94-123">Все перечисленные ниже ресурсы FHIR должны быть доступны по прямой ссылке на ресурс.</span><span class="sxs-lookup"><span data-stu-id="fca94-123">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="fca94-124">Минимальный набор полей, необходимый для установки соответствия</span><span class="sxs-lookup"><span data-stu-id="fca94-124">Conformance minimum required field set</span></span>

 <span data-ttu-id="fca94-125">Сервер FHIR должен реализовать инструкцию соответствия, чтобы получить сводную информацию о ее возможностях factual.</span><span class="sxs-lookup"><span data-stu-id="fca94-125">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="fca94-126">Ниже перечислены параметры на сервере DSTU2 FHIR:</span><span class="sxs-lookup"><span data-stu-id="fca94-126">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="fca94-127">ДЕРЖИВАЕТ</span><span class="sxs-lookup"><span data-stu-id="fca94-127">REST</span></span>

    - <span data-ttu-id="fca94-128">Режиме</span><span class="sxs-lookup"><span data-stu-id="fca94-128">Mode</span></span>
    - <span data-ttu-id="fca94-129">Действует</span><span class="sxs-lookup"><span data-stu-id="fca94-129">Interaction</span></span>
    - <span data-ttu-id="fca94-130">Ресурс: тип</span><span class="sxs-lookup"><span data-stu-id="fca94-130">Resource: Type</span></span>
    - <span data-ttu-id="fca94-131">Безопасность: [расширение URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="fca94-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="fca94-132">FhirVersion (для нашего кода требуется, чтобы узнать, в какую версию следует поворачивать, так как мы поддерживаем несколько версий.)</span><span class="sxs-lookup"><span data-stu-id="fca94-132">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="fca94-133">[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="fca94-133">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="fca94-134">Подождите</span><span class="sxs-lookup"><span data-stu-id="fca94-134">Patient</span></span>

<span data-ttu-id="fca94-135">Это минимальные обязательные поля, которые являются подмножеством полей [профиля пациента Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :</span><span class="sxs-lookup"><span data-stu-id="fca94-135">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="fca94-136">Family (имя)</span><span class="sxs-lookup"><span data-stu-id="fca94-136">Name.Family</span></span>
 - <span data-ttu-id="fca94-137">Name (имя). задано</span><span class="sxs-lookup"><span data-stu-id="fca94-137">Name.Given</span></span>
 - <span data-ttu-id="fca94-138">Полу</span><span class="sxs-lookup"><span data-stu-id="fca94-138">Gender</span></span>
 - <span data-ttu-id="fca94-139">Рождения</span><span class="sxs-lookup"><span data-stu-id="fca94-139">BirthDate</span></span>
 - <span data-ttu-id="fca94-140">MRN (идентификатор)</span><span class="sxs-lookup"><span data-stu-id="fca94-140">MRN (Identifier)</span></span>

<span data-ttu-id="fca94-141">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также считывает следующие поля:</span><span class="sxs-lookup"><span data-stu-id="fca94-141">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="fca94-142">Name. use</span><span class="sxs-lookup"><span data-stu-id="fca94-142">Name.Use</span></span>
 - <span data-ttu-id="fca94-143">Name. prefix</span><span class="sxs-lookup"><span data-stu-id="fca94-143">Name.Prefix</span></span>
 - <span data-ttu-id="fca94-144">CareProvider (эта ссылка на ресурс пациент должна содержать отображаемые поля, показанные в приведенном ниже примере).</span><span class="sxs-lookup"><span data-stu-id="fca94-144">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

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

<span data-ttu-id="fca94-145">Поиск ресурсов использует метод POST по адресу/Patient/_search и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fca94-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="fca94-146">номер</span><span class="sxs-lookup"><span data-stu-id="fca94-146">id</span></span>
 - <span data-ttu-id="fca94-147">Семья: Contains = (ищет все пациентов, чье имя семейства оно содержат.)</span><span class="sxs-lookup"><span data-stu-id="fca94-147">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="fca94-148">указанный =\<substring></span><span class="sxs-lookup"><span data-stu-id="fca94-148">given=\<substring></span></span>
 - <span data-ttu-id="fca94-149">Name =\<substring></span><span class="sxs-lookup"><span data-stu-id="fca94-149">name=\<substring></span></span>
 - <span data-ttu-id="fca94-150">Дата рождения = (точное совпадение)</span><span class="sxs-lookup"><span data-stu-id="fca94-150">birthdate=(exact match)</span></span>
 - <span data-ttu-id="fca94-151">\_Count (максимальное количество возвращаемых результатов)</span><span class="sxs-lookup"><span data-stu-id="fca94-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="fca94-152">Ответ должен содержать общее количество записей, возвращенных в результате поиска, и \_ количество будет использоваться PatientsApp для ограничения количества возвращенных записей.</span><span class="sxs-lookup"><span data-stu-id="fca94-152">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="fca94-153">Идентификатор =\<mrn></span><span class="sxs-lookup"><span data-stu-id="fca94-153">identifier=\<mrn></span></span>

<span data-ttu-id="fca94-154">Цель — найти и отфильтровать пациента в пациент, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="fca94-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="fca94-155">ID: это идентификатор ресурса, который содержит каждый ресурс в FHIR.</span><span class="sxs-lookup"><span data-stu-id="fca94-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="fca94-156">MRN: фактический идентификатор пациента, который будет знать Clinical сотрудника.</span><span class="sxs-lookup"><span data-stu-id="fca94-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="fca94-157">Мы понимаем, что этот MRN основывается на типе идентификатора в ресурсе идентификатора в FHIR</span><span class="sxs-lookup"><span data-stu-id="fca94-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="fca94-158">Имя</span><span class="sxs-lookup"><span data-stu-id="fca94-158">Name</span></span>
- <span data-ttu-id="fca94-159">Рождения</span><span class="sxs-lookup"><span data-stu-id="fca94-159">Birthdate</span></span>

<span data-ttu-id="fca94-160">Ниже приведен пример этого звонка.</span><span class="sxs-lookup"><span data-stu-id="fca94-160">See the following example  of this call.</span></span>

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

<span data-ttu-id="fca94-161">[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="fca94-161">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="fca94-162">Наблюдение</span><span class="sxs-lookup"><span data-stu-id="fca94-162">Observation</span></span>

<span data-ttu-id="fca94-163">Это минимальные обязательные поля, которые являются подмножеством профиля Argonaut важную подпись:</span><span class="sxs-lookup"><span data-stu-id="fca94-163">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="fca94-164">Эффективная (Дата и время)</span><span class="sxs-lookup"><span data-stu-id="fca94-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="fca94-165">Код. кодирование. Code</span><span class="sxs-lookup"><span data-stu-id="fca94-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="fca94-166">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="fca94-166">ValueQuantity.Value</span></span>

<span data-ttu-id="fca94-167">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также считывает следующие поля:</span><span class="sxs-lookup"><span data-stu-id="fca94-167">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="fca94-168">Код. программирование. Display</span><span class="sxs-lookup"><span data-stu-id="fca94-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="fca94-169">ValueQuantity. ед.</span><span class="sxs-lookup"><span data-stu-id="fca94-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="fca94-170">При использовании наблюдения за компонентами одна и та же логика применяется для наблюдения за каждым компонентом.</span><span class="sxs-lookup"><span data-stu-id="fca94-170">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="fca94-171">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fca94-171">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="fca94-172">пациент =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="fca94-172">patient=\<patient id\></span></span>
 - <span data-ttu-id="fca94-173">сортировка: DESC =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="fca94-173">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="fca94-174">Цель состоит в том, чтобы получить последние важные знаки для пациента, [VitalSigns. DSTU. saz] (наблюдение?).</span><span class="sxs-lookup"><span data-stu-id="fca94-174">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

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

<span data-ttu-id="fca94-175">[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="fca94-175">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="fca94-176">Условие</span><span class="sxs-lookup"><span data-stu-id="fca94-176">Condition</span></span>

<span data-ttu-id="fca94-177">Это минимальные обязательные поля, которые являются подмножеством [профиля условия Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="fca94-177">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="fca94-178">Код. кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="fca94-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="fca94-179">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="fca94-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="fca94-180">Дата записи</span><span class="sxs-lookup"><span data-stu-id="fca94-180">Date Recorded</span></span>
 - <span data-ttu-id="fca94-181">Уровню серьезности</span><span class="sxs-lookup"><span data-stu-id="fca94-181">Severity</span></span>

<span data-ttu-id="fca94-182">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fca94-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="fca94-183">пациент =\<patient id></span><span class="sxs-lookup"><span data-stu-id="fca94-183">patient=\<patient id></span></span>
 - <span data-ttu-id="fca94-184">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="fca94-184">_count=\<max results></span></span>

<span data-ttu-id="fca94-185">Ниже приведен пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="fca94-185">See the following example of this call:</span></span>

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

<span data-ttu-id="fca94-186">[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="fca94-186">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="fca94-187">Происходит</span><span class="sxs-lookup"><span data-stu-id="fca94-187">Encounter</span></span>

<span data-ttu-id="fca94-188">Это минимальные обязательные поля, которые являются подмножеством подмножества для основного профиля в США, которое должно иметь следующие поля:</span><span class="sxs-lookup"><span data-stu-id="fca94-188">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="fca94-189">Состояни</span><span class="sxs-lookup"><span data-stu-id="fca94-189">Status</span></span>
 - <span data-ttu-id="fca94-190">Введите [0]. Кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="fca94-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="fca94-191">Кроме того, ниже перечислены поля, которые можно получить из основного приложения US "требуется поддержка".</span><span class="sxs-lookup"><span data-stu-id="fca94-191">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="fca94-192">Period. Start</span><span class="sxs-lookup"><span data-stu-id="fca94-192">Period.Start</span></span>
 - <span data-ttu-id="fca94-193">Расположение [0]. Расположение. Display</span><span class="sxs-lookup"><span data-stu-id="fca94-193">Location[0].Location.Display</span></span>

<span data-ttu-id="fca94-194">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fca94-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="fca94-195">пациент =\<patient id></span><span class="sxs-lookup"><span data-stu-id="fca94-195">patient=\<patient id></span></span>
 - <span data-ttu-id="fca94-196">_sort: DESC =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="fca94-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="fca94-197">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="fca94-197">_count=\<max results></span></span>

<span data-ttu-id="fca94-198">Цель — получить Последнее известное расположение пациента.</span><span class="sxs-lookup"><span data-stu-id="fca94-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="fca94-199">Каждый из этих обнаружений ссылается на ресурс расположения.</span><span class="sxs-lookup"><span data-stu-id="fca94-199">Each encounter references a location resource.</span></span> <span data-ttu-id="fca94-200">Ссылка также должна включать поле отображения местоположения.</span><span class="sxs-lookup"><span data-stu-id="fca94-200">The reference shall also include the location's display field.</span></span> <span data-ttu-id="fca94-201">Ниже приведен пример этого звонка.</span><span class="sxs-lookup"><span data-stu-id="fca94-201">See the following example of this call.</span></span>

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

<span data-ttu-id="fca94-202">[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="fca94-202">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="fca94-203">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="fca94-203">AllergyIntolerance</span></span>

<span data-ttu-id="fca94-204">Это минимальные обязательные поля, которые являются подмножеством профиля Argonaut AllergyIntolerance:</span><span class="sxs-lookup"><span data-stu-id="fca94-204">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="fca94-205">Code. Text</span><span class="sxs-lookup"><span data-stu-id="fca94-205">Code.Text</span></span>
 - <span data-ttu-id="fca94-206">Код. кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="fca94-206">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="fca94-207">Состояни</span><span class="sxs-lookup"><span data-stu-id="fca94-207">Status</span></span>

<span data-ttu-id="fca94-208">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также считывает следующие поля:</span><span class="sxs-lookup"><span data-stu-id="fca94-208">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="fca94-209">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="fca94-209">RecordedDate</span></span>
 - <span data-ttu-id="fca94-210">Примечание. текст</span><span class="sxs-lookup"><span data-stu-id="fca94-210">Note.Text</span></span>
 - <span data-ttu-id="fca94-211">Реакция [..]. Вещество. текст</span><span class="sxs-lookup"><span data-stu-id="fca94-211">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="fca94-212">Реакция [..]. Манифест [..]. Текстовые</span><span class="sxs-lookup"><span data-stu-id="fca94-212">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="fca94-213">Text. Div</span><span class="sxs-lookup"><span data-stu-id="fca94-213">Text.Div</span></span>

<span data-ttu-id="fca94-214">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fca94-214">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="fca94-215">Пациент =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="fca94-215">Patient =  \<patient id></span></span>

<span data-ttu-id="fca94-216">Ниже приведен пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="fca94-216">See the following example of this call:</span></span>

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

<span data-ttu-id="fca94-217">[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="fca94-217">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="fca94-218">Лечения заказ</span><span class="sxs-lookup"><span data-stu-id="fca94-218">Medication Order</span></span>

<span data-ttu-id="fca94-219">Это минимальные обязательные поля, которые являются подмножеством профиля Argonaut MedicationOrder:</span><span class="sxs-lookup"><span data-stu-id="fca94-219">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="fca94-220">DateWritten</span><span class="sxs-lookup"><span data-stu-id="fca94-220">DateWritten</span></span>
 - <span data-ttu-id="fca94-221">Предписанный. Display</span><span class="sxs-lookup"><span data-stu-id="fca94-221">Prescriber.Display</span></span>
 - <span data-ttu-id="fca94-222">Лечения. Display (если ссылка)</span><span class="sxs-lookup"><span data-stu-id="fca94-222">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="fca94-223">Лечения. Text (если понятие)</span><span class="sxs-lookup"><span data-stu-id="fca94-223">Medication.Text (if concept)</span></span>

<span data-ttu-id="fca94-224">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="fca94-224">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="fca94-225">DateEnded</span><span class="sxs-lookup"><span data-stu-id="fca94-225">DateEnded</span></span>
 - <span data-ttu-id="fca94-226">DosageInstruction. Text</span><span class="sxs-lookup"><span data-stu-id="fca94-226">DosageInstruction.Text</span></span>
 - <span data-ttu-id="fca94-227">Text. Div</span><span class="sxs-lookup"><span data-stu-id="fca94-227">Text.Div</span></span>

<span data-ttu-id="fca94-228">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fca94-228">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="fca94-229">пациент =\<patient id></span><span class="sxs-lookup"><span data-stu-id="fca94-229">patient=\<patient id></span></span>
 - <span data-ttu-id="fca94-230">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="fca94-230">_count=\<max results></span></span>

<span data-ttu-id="fca94-231">Ниже приведен пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="fca94-231">See the following example of this call:</span></span>

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

<span data-ttu-id="fca94-232">[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="fca94-232">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="fca94-233">Приложения</span><span class="sxs-lookup"><span data-stu-id="fca94-233">Coverage</span></span>

<span data-ttu-id="fca94-234">Это минимальный обязательный набор полей, не охваченных профилями США или Argonaut:</span><span class="sxs-lookup"><span data-stu-id="fca94-234">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="fca94-235">Payor</span><span class="sxs-lookup"><span data-stu-id="fca94-235">Payor</span></span>

<span data-ttu-id="fca94-236">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fca94-236">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="fca94-237">пациент =\<patient id></span><span class="sxs-lookup"><span data-stu-id="fca94-237">patient=\<patient id></span></span>

<span data-ttu-id="fca94-238">Ниже приведен пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="fca94-238">See the following example of this call:</span></span>

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
    
<span data-ttu-id="fca94-239">[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="fca94-239">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="fca94-240">Местоположение</span><span class="sxs-lookup"><span data-stu-id="fca94-240">Location</span></span>

<span data-ttu-id="fca94-241">Этот ресурс используется только в качестве ссылки на ресурс " [встреча](#encounter) ".</span><span class="sxs-lookup"><span data-stu-id="fca94-241">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="fca94-242">[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="fca94-242">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
