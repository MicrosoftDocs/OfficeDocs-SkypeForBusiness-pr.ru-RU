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
ms.openlocfilehash: 12833ea55977cf7e8d18ee5c10b1f17d898b27b3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803487"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="03e3e-103">Характеристики интерфейса DSTU2</span><span class="sxs-lookup"><span data-stu-id="03e3e-103">DSTU2 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="03e3e-104">Действительно 30 октября 2020 г. приложение пациентов было прекращено и заменено [приложением "списки](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) " в Teams.</span><span class="sxs-lookup"><span data-stu-id="03e3e-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="03e3e-105">Данные приложения пациентов хранятся в почтовом ящике группы Office 365, которая является резервной командой.</span><span class="sxs-lookup"><span data-stu-id="03e3e-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="03e3e-106">Все данные, связанные с приложением пациентов, сохраняются в этой группе, но их больше нельзя будет получить с помощью пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="03e3e-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="03e3e-107">Пользователи могут повторно создавать списки с помощью приложения " [списки](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)".</span><span class="sxs-lookup"><span data-stu-id="03e3e-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="03e3e-108">Благодаря спискам, благодаря вашим командам в организации здравоохранения вы сможете создавать списки пациент для сценариев, начиная с округляющих и interdisciplinaryных собраний групп и заканчивая общим мониторингом пациента.</span><span class="sxs-lookup"><span data-stu-id="03e3e-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="03e3e-109">Чтобы приступить к работе, изучите шаблон пациентов в списках.</span><span class="sxs-lookup"><span data-stu-id="03e3e-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="03e3e-110">Дополнительные сведения об управлении приложением Lists в Организации можно найти в разделе [Управление приложением "списки"](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="03e3e-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="03e3e-111">Настройка или перенастройка сервера FHIR для работы с приложением Microsoft Teams пациентов требует понимания данных, к которым приложению требуется доступ.</span><span class="sxs-lookup"><span data-stu-id="03e3e-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="03e3e-112">Сервер FHIR должен поддерживать запросы POST, используя пакеты для указанных ниже ресурсов.</span><span class="sxs-lookup"><span data-stu-id="03e3e-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="03e3e-113">Подождите</span><span class="sxs-lookup"><span data-stu-id="03e3e-113">Patient</span></span>](#patient)
- [<span data-ttu-id="03e3e-114">Наблюдение</span><span class="sxs-lookup"><span data-stu-id="03e3e-114">Observation</span></span>](#observation)
- [<span data-ttu-id="03e3e-115">Условие</span><span class="sxs-lookup"><span data-stu-id="03e3e-115">Condition</span></span>](#condition)
- [<span data-ttu-id="03e3e-116">Происходит</span><span class="sxs-lookup"><span data-stu-id="03e3e-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="03e3e-117">Недопустимый Allergy</span><span class="sxs-lookup"><span data-stu-id="03e3e-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="03e3e-118">Приложения</span><span class="sxs-lookup"><span data-stu-id="03e3e-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="03e3e-119">Лечения заказ</span><span class="sxs-lookup"><span data-stu-id="03e3e-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="03e3e-120">Расположение</span><span class="sxs-lookup"><span data-stu-id="03e3e-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="03e3e-121">Ресурс пациент является единственным обязательным ресурсом (без которого приложение не будет загружаться вообще).</span><span class="sxs-lookup"><span data-stu-id="03e3e-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="03e3e-122">Тем не менее, рекомендуется, чтобы партнеры реализовали поддержку всех вышеупомянутых ресурсов для спецификаций, указанных ниже, для наилучшего взаимодействия с пользователем в приложении Microsoft Teams пациентов.</span><span class="sxs-lookup"><span data-stu-id="03e3e-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="03e3e-123">Запросы из приложения Microsoft Teams пациентов для нескольких ресурсов. отправляет набор (пакет) запросов на URL-адрес сервера FHIR.</span><span class="sxs-lookup"><span data-stu-id="03e3e-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="03e3e-124">Сервер обрабатывает каждый запрос и возвращает набор ресурсов, соответствующих каждому запросу.</span><span class="sxs-lookup"><span data-stu-id="03e3e-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="03e3e-125">Дополнительные сведения и примеры можно найти в разделе [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="03e3e-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="03e3e-126">Все перечисленные ниже ресурсы FHIR должны быть доступны по прямой ссылке на ресурс.</span><span class="sxs-lookup"><span data-stu-id="03e3e-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="03e3e-127">Минимальный набор полей, необходимый для установки соответствия</span><span class="sxs-lookup"><span data-stu-id="03e3e-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="03e3e-128">Сервер FHIR должен реализовать инструкцию соответствия, чтобы получить сводную информацию о ее возможностях factual.</span><span class="sxs-lookup"><span data-stu-id="03e3e-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="03e3e-129">Ниже перечислены параметры на сервере DSTU2 FHIR:</span><span class="sxs-lookup"><span data-stu-id="03e3e-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="03e3e-130">ДЕРЖИВАЕТ</span><span class="sxs-lookup"><span data-stu-id="03e3e-130">REST</span></span>

    - <span data-ttu-id="03e3e-131">Режиме</span><span class="sxs-lookup"><span data-stu-id="03e3e-131">Mode</span></span>
    - <span data-ttu-id="03e3e-132">Действует</span><span class="sxs-lookup"><span data-stu-id="03e3e-132">Interaction</span></span>
    - <span data-ttu-id="03e3e-133">Ресурс: тип</span><span class="sxs-lookup"><span data-stu-id="03e3e-133">Resource: Type</span></span>
    - <span data-ttu-id="03e3e-134">Безопасность: [расширение URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="03e3e-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="03e3e-135">FhirVersion (для нашего кода требуется, чтобы узнать, в какую версию следует поворачивать, так как мы поддерживаем несколько версий.)</span><span class="sxs-lookup"><span data-stu-id="03e3e-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="03e3e-136">[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="03e3e-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="03e3e-137">Подождите</span><span class="sxs-lookup"><span data-stu-id="03e3e-137">Patient</span></span>

<span data-ttu-id="03e3e-138">Это минимальные обязательные поля, которые являются подмножеством полей [профиля пациента Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :</span><span class="sxs-lookup"><span data-stu-id="03e3e-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="03e3e-139">Family (имя)</span><span class="sxs-lookup"><span data-stu-id="03e3e-139">Name.Family</span></span>
 - <span data-ttu-id="03e3e-140">Name (имя). задано</span><span class="sxs-lookup"><span data-stu-id="03e3e-140">Name.Given</span></span>
 - <span data-ttu-id="03e3e-141">Полу</span><span class="sxs-lookup"><span data-stu-id="03e3e-141">Gender</span></span>
 - <span data-ttu-id="03e3e-142">Рождения</span><span class="sxs-lookup"><span data-stu-id="03e3e-142">BirthDate</span></span>
 - <span data-ttu-id="03e3e-143">MRN (идентификатор)</span><span class="sxs-lookup"><span data-stu-id="03e3e-143">MRN (Identifier)</span></span>

<span data-ttu-id="03e3e-144">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также считывает следующие поля:</span><span class="sxs-lookup"><span data-stu-id="03e3e-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="03e3e-145">Name. use</span><span class="sxs-lookup"><span data-stu-id="03e3e-145">Name.Use</span></span>
 - <span data-ttu-id="03e3e-146">Name. prefix</span><span class="sxs-lookup"><span data-stu-id="03e3e-146">Name.Prefix</span></span>
 - <span data-ttu-id="03e3e-147">CareProvider (эта ссылка на ресурс пациент должна содержать отображаемые поля, показанные в приведенном ниже примере).</span><span class="sxs-lookup"><span data-stu-id="03e3e-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

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

<span data-ttu-id="03e3e-148">Поиск ресурсов использует метод POST по адресу/Patient/_search и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="03e3e-148">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="03e3e-149">номер</span><span class="sxs-lookup"><span data-stu-id="03e3e-149">id</span></span>
 - <span data-ttu-id="03e3e-150">Семья: Contains = (ищет все пациентов, чье имя семейства оно содержат.)</span><span class="sxs-lookup"><span data-stu-id="03e3e-150">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="03e3e-151">указанный =\<substring></span><span class="sxs-lookup"><span data-stu-id="03e3e-151">given=\<substring></span></span>
 - <span data-ttu-id="03e3e-152">Name =\<substring></span><span class="sxs-lookup"><span data-stu-id="03e3e-152">name=\<substring></span></span>
 - <span data-ttu-id="03e3e-153">Дата рождения = (точное совпадение)</span><span class="sxs-lookup"><span data-stu-id="03e3e-153">birthdate=(exact match)</span></span>
 - <span data-ttu-id="03e3e-154">\_Count (максимальное количество возвращаемых результатов)</span><span class="sxs-lookup"><span data-stu-id="03e3e-154">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="03e3e-155">Ответ должен содержать общее количество записей, возвращенных в результате поиска, и \_ количество будет использоваться PatientsApp для ограничения количества возвращенных записей.</span><span class="sxs-lookup"><span data-stu-id="03e3e-155">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="03e3e-156">Идентификатор =\<mrn></span><span class="sxs-lookup"><span data-stu-id="03e3e-156">identifier=\<mrn></span></span>

<span data-ttu-id="03e3e-157">Цель — найти и отфильтровать пациента в пациент, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="03e3e-157">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="03e3e-158">ID: это идентификатор ресурса, который содержит каждый ресурс в FHIR.</span><span class="sxs-lookup"><span data-stu-id="03e3e-158">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="03e3e-159">MRN: фактический идентификатор пациента, который будет знать Clinical сотрудника.</span><span class="sxs-lookup"><span data-stu-id="03e3e-159">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="03e3e-160">Мы понимаем, что этот MRN основывается на типе идентификатора в ресурсе идентификатора в FHIR</span><span class="sxs-lookup"><span data-stu-id="03e3e-160">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="03e3e-161">Имя</span><span class="sxs-lookup"><span data-stu-id="03e3e-161">Name</span></span>
- <span data-ttu-id="03e3e-162">Рождения</span><span class="sxs-lookup"><span data-stu-id="03e3e-162">Birthdate</span></span>

<span data-ttu-id="03e3e-163">Ниже приведен пример этого звонка.</span><span class="sxs-lookup"><span data-stu-id="03e3e-163">See the following example  of this call.</span></span>

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

<span data-ttu-id="03e3e-164">[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="03e3e-164">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="03e3e-165">Наблюдение</span><span class="sxs-lookup"><span data-stu-id="03e3e-165">Observation</span></span>

<span data-ttu-id="03e3e-166">Это минимальные обязательные поля, которые являются подмножеством профиля Argonaut важную подпись:</span><span class="sxs-lookup"><span data-stu-id="03e3e-166">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="03e3e-167">Эффективная (Дата и время)</span><span class="sxs-lookup"><span data-stu-id="03e3e-167">Effective (date time or period)</span></span>
 - <span data-ttu-id="03e3e-168">Код. кодирование. Code</span><span class="sxs-lookup"><span data-stu-id="03e3e-168">Code.Coding.Code</span></span>
 - <span data-ttu-id="03e3e-169">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="03e3e-169">ValueQuantity.Value</span></span>

<span data-ttu-id="03e3e-170">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также считывает следующие поля:</span><span class="sxs-lookup"><span data-stu-id="03e3e-170">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="03e3e-171">Код. программирование. Display</span><span class="sxs-lookup"><span data-stu-id="03e3e-171">Code.Coding.Display</span></span>
 - <span data-ttu-id="03e3e-172">ValueQuantity. ед.</span><span class="sxs-lookup"><span data-stu-id="03e3e-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="03e3e-173">При использовании наблюдения за компонентами одна и та же логика применяется для наблюдения за каждым компонентом.</span><span class="sxs-lookup"><span data-stu-id="03e3e-173">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="03e3e-174">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="03e3e-174">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="03e3e-175">пациент =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="03e3e-175">patient=\<patient id\></span></span>
 - <span data-ttu-id="03e3e-176">сортировка: DESC =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="03e3e-176">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="03e3e-177">Цель состоит в том, чтобы получить последние важные знаки для пациента, [VitalSigns. DSTU. saz] (наблюдение?).</span><span class="sxs-lookup"><span data-stu-id="03e3e-177">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

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

<span data-ttu-id="03e3e-178">[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="03e3e-178">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="03e3e-179">Условие</span><span class="sxs-lookup"><span data-stu-id="03e3e-179">Condition</span></span>

<span data-ttu-id="03e3e-180">Это минимальные обязательные поля, которые являются подмножеством [профиля условия Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="03e3e-180">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="03e3e-181">Код. кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="03e3e-181">Code.Coding[0].Display</span></span>

<span data-ttu-id="03e3e-182">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="03e3e-182">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="03e3e-183">Дата записи</span><span class="sxs-lookup"><span data-stu-id="03e3e-183">Date Recorded</span></span>
 - <span data-ttu-id="03e3e-184">Уровню серьезности</span><span class="sxs-lookup"><span data-stu-id="03e3e-184">Severity</span></span>

<span data-ttu-id="03e3e-185">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="03e3e-185">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="03e3e-186">пациент =\<patient id></span><span class="sxs-lookup"><span data-stu-id="03e3e-186">patient=\<patient id></span></span>
 - <span data-ttu-id="03e3e-187">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="03e3e-187">_count=\<max results></span></span>

<span data-ttu-id="03e3e-188">Ниже приведен пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="03e3e-188">See the following example of this call:</span></span>

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

<span data-ttu-id="03e3e-189">[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="03e3e-189">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="03e3e-190">Происходит</span><span class="sxs-lookup"><span data-stu-id="03e3e-190">Encounter</span></span>

<span data-ttu-id="03e3e-191">Это минимальные обязательные поля, которые являются подмножеством подмножества для основного профиля в США, которое должно иметь следующие поля:</span><span class="sxs-lookup"><span data-stu-id="03e3e-191">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="03e3e-192">Состояни</span><span class="sxs-lookup"><span data-stu-id="03e3e-192">Status</span></span>
 - <span data-ttu-id="03e3e-193">Введите [0]. Кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="03e3e-193">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="03e3e-194">Кроме того, ниже перечислены поля, которые можно получить из основного приложения US "требуется поддержка".</span><span class="sxs-lookup"><span data-stu-id="03e3e-194">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="03e3e-195">Period. Start</span><span class="sxs-lookup"><span data-stu-id="03e3e-195">Period.Start</span></span>
 - <span data-ttu-id="03e3e-196">Расположение [0]. Расположение. Display</span><span class="sxs-lookup"><span data-stu-id="03e3e-196">Location[0].Location.Display</span></span>

<span data-ttu-id="03e3e-197">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="03e3e-197">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="03e3e-198">пациент =\<patient id></span><span class="sxs-lookup"><span data-stu-id="03e3e-198">patient=\<patient id></span></span>
 - <span data-ttu-id="03e3e-199">_sort: DESC =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="03e3e-199">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="03e3e-200">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="03e3e-200">_count=\<max results></span></span>

<span data-ttu-id="03e3e-201">Цель — получить Последнее известное расположение пациента.</span><span class="sxs-lookup"><span data-stu-id="03e3e-201">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="03e3e-202">Каждый из этих обнаружений ссылается на ресурс расположения.</span><span class="sxs-lookup"><span data-stu-id="03e3e-202">Each encounter references a location resource.</span></span> <span data-ttu-id="03e3e-203">Ссылка также должна включать поле отображения местоположения.</span><span class="sxs-lookup"><span data-stu-id="03e3e-203">The reference shall also include the location's display field.</span></span> <span data-ttu-id="03e3e-204">Ниже приведен пример этого звонка.</span><span class="sxs-lookup"><span data-stu-id="03e3e-204">See the following example of this call.</span></span>

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

<span data-ttu-id="03e3e-205">[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="03e3e-205">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="03e3e-206">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="03e3e-206">AllergyIntolerance</span></span>

<span data-ttu-id="03e3e-207">Это минимальные обязательные поля, которые являются подмножеством профиля Argonaut AllergyIntolerance:</span><span class="sxs-lookup"><span data-stu-id="03e3e-207">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="03e3e-208">Code. Text</span><span class="sxs-lookup"><span data-stu-id="03e3e-208">Code.Text</span></span>
 - <span data-ttu-id="03e3e-209">Код. кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="03e3e-209">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="03e3e-210">Состояни</span><span class="sxs-lookup"><span data-stu-id="03e3e-210">Status</span></span>

<span data-ttu-id="03e3e-211">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также считывает следующие поля:</span><span class="sxs-lookup"><span data-stu-id="03e3e-211">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="03e3e-212">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="03e3e-212">RecordedDate</span></span>
 - <span data-ttu-id="03e3e-213">Примечание. текст</span><span class="sxs-lookup"><span data-stu-id="03e3e-213">Note.Text</span></span>
 - <span data-ttu-id="03e3e-214">Реакция [..]. Вещество. текст</span><span class="sxs-lookup"><span data-stu-id="03e3e-214">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="03e3e-215">Реакция [..]. Манифест [..]. Текстовые</span><span class="sxs-lookup"><span data-stu-id="03e3e-215">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="03e3e-216">Text. Div</span><span class="sxs-lookup"><span data-stu-id="03e3e-216">Text.Div</span></span>

<span data-ttu-id="03e3e-217">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="03e3e-217">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="03e3e-218">Пациент =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="03e3e-218">Patient =  \<patient id></span></span>

<span data-ttu-id="03e3e-219">Ниже приведен пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="03e3e-219">See the following example of this call:</span></span>

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

<span data-ttu-id="03e3e-220">[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="03e3e-220">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="03e3e-221">Лечения заказ</span><span class="sxs-lookup"><span data-stu-id="03e3e-221">Medication Order</span></span>

<span data-ttu-id="03e3e-222">Это минимальные обязательные поля, которые являются подмножеством профиля Argonaut MedicationOrder:</span><span class="sxs-lookup"><span data-stu-id="03e3e-222">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="03e3e-223">DateWritten</span><span class="sxs-lookup"><span data-stu-id="03e3e-223">DateWritten</span></span>
 - <span data-ttu-id="03e3e-224">Предписанный. Display</span><span class="sxs-lookup"><span data-stu-id="03e3e-224">Prescriber.Display</span></span>
 - <span data-ttu-id="03e3e-225">Лечения. Display (если ссылка)</span><span class="sxs-lookup"><span data-stu-id="03e3e-225">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="03e3e-226">Лечения. Text (если понятие)</span><span class="sxs-lookup"><span data-stu-id="03e3e-226">Medication.Text (if concept)</span></span>

<span data-ttu-id="03e3e-227">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="03e3e-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="03e3e-228">DateEnded</span><span class="sxs-lookup"><span data-stu-id="03e3e-228">DateEnded</span></span>
 - <span data-ttu-id="03e3e-229">DosageInstruction. Text</span><span class="sxs-lookup"><span data-stu-id="03e3e-229">DosageInstruction.Text</span></span>
 - <span data-ttu-id="03e3e-230">Text. Div</span><span class="sxs-lookup"><span data-stu-id="03e3e-230">Text.Div</span></span>

<span data-ttu-id="03e3e-231">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="03e3e-231">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="03e3e-232">пациент =\<patient id></span><span class="sxs-lookup"><span data-stu-id="03e3e-232">patient=\<patient id></span></span>
 - <span data-ttu-id="03e3e-233">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="03e3e-233">_count=\<max results></span></span>

<span data-ttu-id="03e3e-234">Ниже приведен пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="03e3e-234">See the following example of this call:</span></span>

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

<span data-ttu-id="03e3e-235">[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="03e3e-235">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="03e3e-236">Приложения</span><span class="sxs-lookup"><span data-stu-id="03e3e-236">Coverage</span></span>

<span data-ttu-id="03e3e-237">Это минимальный обязательный набор полей, не охваченных профилями США или Argonaut:</span><span class="sxs-lookup"><span data-stu-id="03e3e-237">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="03e3e-238">Payor</span><span class="sxs-lookup"><span data-stu-id="03e3e-238">Payor</span></span>

<span data-ttu-id="03e3e-239">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="03e3e-239">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="03e3e-240">пациент =\<patient id></span><span class="sxs-lookup"><span data-stu-id="03e3e-240">patient=\<patient id></span></span>

<span data-ttu-id="03e3e-241">Ниже приведен пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="03e3e-241">See the following example of this call:</span></span>

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
    
<span data-ttu-id="03e3e-242">[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="03e3e-242">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="03e3e-243">Местоположение</span><span class="sxs-lookup"><span data-stu-id="03e3e-243">Location</span></span>

<span data-ttu-id="03e3e-244">Этот ресурс используется только в качестве ссылки на ресурс " [встреча](#encounter) ".</span><span class="sxs-lookup"><span data-stu-id="03e3e-244">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="03e3e-245">[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="03e3e-245">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
