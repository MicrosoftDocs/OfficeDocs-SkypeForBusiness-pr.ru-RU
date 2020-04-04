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
ms.openlocfilehash: f09f43af431b3f0cc6d9f984171206f2549a550a
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136959"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="ac135-103">Характеристики интерфейса DSTU2</span><span class="sxs-lookup"><span data-stu-id="ac135-103">DSTU2 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="ac135-104">Настройка или перенастройка сервера FHIR для работы с приложением Microsoft Teams пациентов требует понимания данных, к которым приложению требуется доступ.</span><span class="sxs-lookup"><span data-stu-id="ac135-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="ac135-105">Сервер FHIR должен поддерживать запросы POST, используя пакеты для указанных ниже ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ac135-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="ac135-106">Подождите</span><span class="sxs-lookup"><span data-stu-id="ac135-106">Patient</span></span>](#patient)
- [<span data-ttu-id="ac135-107">Наблюдение</span><span class="sxs-lookup"><span data-stu-id="ac135-107">Observation</span></span>](#observation)
- [<span data-ttu-id="ac135-108">Условие</span><span class="sxs-lookup"><span data-stu-id="ac135-108">Condition</span></span>](#condition)
- [<span data-ttu-id="ac135-109">Происходит</span><span class="sxs-lookup"><span data-stu-id="ac135-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="ac135-110">Недопустимый Allergy</span><span class="sxs-lookup"><span data-stu-id="ac135-110">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="ac135-111">Приложения</span><span class="sxs-lookup"><span data-stu-id="ac135-111">Coverage</span></span>](#coverage)
- [<span data-ttu-id="ac135-112">Лечения заказ</span><span class="sxs-lookup"><span data-stu-id="ac135-112">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="ac135-113">Расположение</span><span class="sxs-lookup"><span data-stu-id="ac135-113">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="ac135-114">Ресурс пациент является единственным обязательным ресурсом (без которого приложение не будет загружаться вообще).</span><span class="sxs-lookup"><span data-stu-id="ac135-114">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="ac135-115">Тем не менее, рекомендуется, чтобы партнеры реализовали поддержку всех вышеупомянутых ресурсов для спецификаций, указанных ниже, для наилучшего взаимодействия с пользователем в приложении Microsoft Teams пациентов.</span><span class="sxs-lookup"><span data-stu-id="ac135-115">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="ac135-116">Запросы из приложения Microsoft Teams пациентов для нескольких ресурсов. отправляет набор (пакет) запросов на URL-адрес сервера FHIR.</span><span class="sxs-lookup"><span data-stu-id="ac135-116">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="ac135-117">Сервер обрабатывает каждый запрос и возвращает набор ресурсов, соответствующих каждому запросу.</span><span class="sxs-lookup"><span data-stu-id="ac135-117">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="ac135-118">Дополнительные сведения и примеры можно найти в [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction)разделе.</span><span class="sxs-lookup"><span data-stu-id="ac135-118">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="ac135-119">Все перечисленные ниже ресурсы FHIR должны быть доступны по прямой ссылке на ресурс.</span><span class="sxs-lookup"><span data-stu-id="ac135-119">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="ac135-120">Минимальный набор полей, необходимый для установки соответствия</span><span class="sxs-lookup"><span data-stu-id="ac135-120">Conformance minimum required field set</span></span>

 <span data-ttu-id="ac135-121">Сервер FHIR должен реализовать инструкцию соответствия, чтобы получить сводную информацию о ее возможностях factual.</span><span class="sxs-lookup"><span data-stu-id="ac135-121">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="ac135-122">Ниже перечислены параметры на сервере DSTU2 FHIR:</span><span class="sxs-lookup"><span data-stu-id="ac135-122">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="ac135-123">ДЕРЖИВАЕТ</span><span class="sxs-lookup"><span data-stu-id="ac135-123">REST</span></span>
   1. <span data-ttu-id="ac135-124">Режиме</span><span class="sxs-lookup"><span data-stu-id="ac135-124">Mode</span></span>
   2. <span data-ttu-id="ac135-125">Действует</span><span class="sxs-lookup"><span data-stu-id="ac135-125">Interaction</span></span>
   3. <span data-ttu-id="ac135-126">Ресурс: тип</span><span class="sxs-lookup"><span data-stu-id="ac135-126">Resource: Type</span></span>
   4. <span data-ttu-id="ac135-127">Безопасность: [расширение URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="ac135-127">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="ac135-128">FhirVersion (для нашего кода требуется, чтобы узнать, в какую версию следует поворачивать, так как мы поддерживаем несколько версий.)</span><span class="sxs-lookup"><span data-stu-id="ac135-128">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="ac135-129">Дополнительные [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="ac135-129">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="ac135-130">Подождите</span><span class="sxs-lookup"><span data-stu-id="ac135-130">Patient</span></span>

<span data-ttu-id="ac135-131">Это минимальные обязательные поля, которые являются подмножеством полей [профиля пациента Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :</span><span class="sxs-lookup"><span data-stu-id="ac135-131">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="ac135-132">Family (имя)</span><span class="sxs-lookup"><span data-stu-id="ac135-132">Name.Family</span></span>
2. <span data-ttu-id="ac135-133">Name (имя). задано</span><span class="sxs-lookup"><span data-stu-id="ac135-133">Name.Given</span></span>
3. <span data-ttu-id="ac135-134">Полу</span><span class="sxs-lookup"><span data-stu-id="ac135-134">Gender</span></span>
4. <span data-ttu-id="ac135-135">Рождения</span><span class="sxs-lookup"><span data-stu-id="ac135-135">BirthDate</span></span>
5. <span data-ttu-id="ac135-136">MRN (идентификатор)</span><span class="sxs-lookup"><span data-stu-id="ac135-136">MRN (Identifier)</span></span>

<span data-ttu-id="ac135-137">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также считывает следующие поля:</span><span class="sxs-lookup"><span data-stu-id="ac135-137">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="ac135-138">Name. use</span><span class="sxs-lookup"><span data-stu-id="ac135-138">Name.Use</span></span>
2. <span data-ttu-id="ac135-139">Name. prefix</span><span class="sxs-lookup"><span data-stu-id="ac135-139">Name.Prefix</span></span>
3. <span data-ttu-id="ac135-140">CareProvider (эта ссылка на ресурс пациент должна содержать отображаемые поля, показанные в приведенном ниже примере).</span><span class="sxs-lookup"><span data-stu-id="ac135-140">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="ac135-141">Запрос: получение <fhir-Server>/Patient/<пациент-ID></span><span class="sxs-lookup"><span data-stu-id="ac135-141">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="ac135-142">Ответ: {"resourceType": "Patient", "идентификатор": "<пациент-ID>";.</span><span class="sxs-lookup"><span data-stu-id="ac135-142">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="ac135-143">.</span><span class="sxs-lookup"><span data-stu-id="ac135-143">.</span></span>
      <span data-ttu-id="ac135-144">.</span><span class="sxs-lookup"><span data-stu-id="ac135-144">.</span></span>
      <span data-ttu-id="ac135-145">"имя": [{"use": "официальный", "префикс": ["MR"], "Family": ["Hugh"] "," ". [" Chau "]}]," идентификатор ": [{" использование ":" официальный "," тип ": {" программирование ": [{" System ":"https://hl7.org/fhir/v2/0203";" код ":" MR "}]};" значение ":" м ";" careProvider ": [{" Display ":" Джейн Петров "}],} 1234567 1957-06-05</span><span class="sxs-lookup"><span data-stu-id="ac135-145">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="ac135-146">Поиск ресурсов использует метод POST по адресу/Patient/_search и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="ac135-146">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="ac135-147">номер</span><span class="sxs-lookup"><span data-stu-id="ac135-147">id</span></span>
2. <span data-ttu-id="ac135-148">Семья: Contains = (ищет все пациентов, чье имя семейства оно содержат.)</span><span class="sxs-lookup"><span data-stu-id="ac135-148">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="ac135-149">заданный\<= подстрока></span><span class="sxs-lookup"><span data-stu-id="ac135-149">given=\<substring></span></span>
4. <span data-ttu-id="ac135-150">Name =\<substring></span><span class="sxs-lookup"><span data-stu-id="ac135-150">name=\<substring></span></span>
5. <span data-ttu-id="ac135-151">Дата рождения = (точное совпадение)</span><span class="sxs-lookup"><span data-stu-id="ac135-151">birthdate=(exact match)</span></span>
6. <span data-ttu-id="ac135-152">\_Count (максимальное количество возвращаемых результатов)</span><span class="sxs-lookup"><span data-stu-id="ac135-152">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="ac135-153">Ответ должен содержать общее количество записей, возвращенных в результате поиска, и \_количество будет использоваться PatientsApp для ограничения количества возвращенных записей.</span><span class="sxs-lookup"><span data-stu-id="ac135-153">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="ac135-154">Идентификатор =\<MRN></span><span class="sxs-lookup"><span data-stu-id="ac135-154">identifier=\<mrn></span></span>

<span data-ttu-id="ac135-155">Цель — найти и отфильтровать пациента в пациент, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ac135-155">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="ac135-156">ID: это идентификатор ресурса, который содержит каждый ресурс в FHIR.</span><span class="sxs-lookup"><span data-stu-id="ac135-156">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="ac135-157">MRN: фактический идентификатор пациента, который будет знать Clinical сотрудника.</span><span class="sxs-lookup"><span data-stu-id="ac135-157">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="ac135-158">Мы понимаем, что этот MRN основывается на типе идентификатора в ресурсе идентификатора в FHIR</span><span class="sxs-lookup"><span data-stu-id="ac135-158">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="ac135-159">Имя</span><span class="sxs-lookup"><span data-stu-id="ac135-159">Name</span></span>
- <span data-ttu-id="ac135-160">Рождения</span><span class="sxs-lookup"><span data-stu-id="ac135-160">Birthdate</span></span>

<span data-ttu-id="ac135-161">Ниже приведен пример этого звонка.</span><span class="sxs-lookup"><span data-stu-id="ac135-161">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="ac135-162">Запрос: POST <fhir-Server>/Patient/_search запроса: с указанным = Hugh&Family = Chau</span><span class="sxs-lookup"><span data-stu-id="ac135-162">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="ac135-163">Response: {"resourceType": "пакет", "идентификатор": "<-ID пакета>".</span><span class="sxs-lookup"><span data-stu-id="ac135-163">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="ac135-164">.</span><span class="sxs-lookup"><span data-stu-id="ac135-164">.</span></span>
      <span data-ttu-id="ac135-165">.</span><span class="sxs-lookup"><span data-stu-id="ac135-165">.</span></span>
      <span data-ttu-id="ac135-166">"Entry": [{"ресурс": {"resourceType": "пациент"; "идентификатор": "<пациент-ID>", "имя": [{"текст": "Hugh Chau", "семья": ["Chau"], ""--"," Дата ":" м ":"----------"1957-06-05</span><span class="sxs-lookup"><span data-stu-id="ac135-166">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="ac135-167">Дополнительные [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="ac135-167">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="ac135-168">Наблюдение</span><span class="sxs-lookup"><span data-stu-id="ac135-168">Observation</span></span>

<span data-ttu-id="ac135-169">Это минимальные обязательные поля, которые являются подмножеством профиля Argonaut важную подпись:</span><span class="sxs-lookup"><span data-stu-id="ac135-169">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="ac135-170">Эффективная (Дата и время)</span><span class="sxs-lookup"><span data-stu-id="ac135-170">Effective (date time or period)</span></span>
 2. <span data-ttu-id="ac135-171">Код. кодирование. Code</span><span class="sxs-lookup"><span data-stu-id="ac135-171">Code.Coding.Code</span></span>
 3. <span data-ttu-id="ac135-172">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="ac135-172">ValueQuantity.Value</span></span>

<span data-ttu-id="ac135-173">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также считывает следующие поля:</span><span class="sxs-lookup"><span data-stu-id="ac135-173">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="ac135-174">Код. программирование. Display</span><span class="sxs-lookup"><span data-stu-id="ac135-174">Code.Coding.Display</span></span>
 2. <span data-ttu-id="ac135-175">ValueQuantity. ед.</span><span class="sxs-lookup"><span data-stu-id="ac135-175">ValueQuantity.Unit</span></span>

<span data-ttu-id="ac135-176">При использовании наблюдения за компонентами одна и та же логика применяется для наблюдения за каждым компонентом.</span><span class="sxs-lookup"><span data-stu-id="ac135-176">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="ac135-177">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="ac135-177">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="ac135-178">пациент =\<ИД пациента\></span><span class="sxs-lookup"><span data-stu-id="ac135-178">patient=\<patient id\></span></span>
2. <span data-ttu-id="ac135-179">Sort: DESC =\<поле ex.</span><span class="sxs-lookup"><span data-stu-id="ac135-179">sort:desc=\<field ex.</span></span> <span data-ttu-id="ac135-180">окончания\></span><span class="sxs-lookup"><span data-stu-id="ac135-180">date\></span></span>

<span data-ttu-id="ac135-181">Цель состоит в том, чтобы получить последние важные знаки для пациента, [VitalSigns. DSTU. saz] (наблюдение?).</span><span class="sxs-lookup"><span data-stu-id="ac135-181">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="ac135-182">Запрос: GET <fhir-Server>/Observation? пациент =<пациент-ID>&_sort:d ESC = Дата&Category = важные-признаки</span><span class="sxs-lookup"><span data-stu-id="ac135-182">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="ac135-183">Response: {"resourceType": "пакет", "идентификатор": <"пакет-ID>", "введите": ",", "," Итого ": 20," Entry ": [{" ресурс ": {" resourceType ":" наблюдение "," идентификатор ":" <ресурс-идентификатор> ";" Категория ": {" программирование ": [{code": "важные-знаки"}],}, "код": {"программирование": [{"Systemhttp://loinc.org": ""; "код": "39156-5", "Display": "BMI"}],}, "effectiveDateTime": "2009-12-01"; "valueQuantity": {"значение": 34,4; "единица": "кг/m2", "http://unitsofmeasure.orgсистема": "кг/m2"}},},.</span><span class="sxs-lookup"><span data-stu-id="ac135-183">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="ac135-184">.</span><span class="sxs-lookup"><span data-stu-id="ac135-184">.</span></span>
        <span data-ttu-id="ac135-185">.</span><span class="sxs-lookup"><span data-stu-id="ac135-185">.</span></span>
      <span data-ttu-id="ac135-186">] }</span><span class="sxs-lookup"><span data-stu-id="ac135-186">] }</span></span>

* * *

<span data-ttu-id="ac135-187">Дополнительные [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="ac135-187">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="ac135-188">Условие</span><span class="sxs-lookup"><span data-stu-id="ac135-188">Condition</span></span>

<span data-ttu-id="ac135-189">Это минимальные обязательные поля, которые являются подмножеством [профиля условия Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="ac135-189">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="ac135-190">Код. кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="ac135-190">Code.Coding[0].Display</span></span>

<span data-ttu-id="ac135-191">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="ac135-191">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="ac135-192">Дата записи</span><span class="sxs-lookup"><span data-stu-id="ac135-192">Date Recorded</span></span>
2. <span data-ttu-id="ac135-193">Уровню серьезности</span><span class="sxs-lookup"><span data-stu-id="ac135-193">Severity</span></span>

<span data-ttu-id="ac135-194">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="ac135-194">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="ac135-195">пациент =\<patient ID></span><span class="sxs-lookup"><span data-stu-id="ac135-195">patient=\<patient id></span></span>
2. <span data-ttu-id="ac135-196">_count =\<максимальное число результатов></span><span class="sxs-lookup"><span data-stu-id="ac135-196">_count=\<max results></span></span>

<span data-ttu-id="ac135-197">Ниже приведен пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="ac135-197">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="ac135-198">Запрос: GET <fhir-Server>/Condition? пациент =<пациент-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="ac135-198">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="ac135-199">Response: {"resourceType": "пакет", "идентификатор <": "набор-ID>", "тип": "набор поиска", "Итого", "элемент": [{"ресурс": {"имя ресурса": "условие", "идентификатор": "<Resource-id>", "код": {"программирование": [{"System": "http://snomed.info/sct", "код": "386033004", "Display": "Neuropathy (Nerve)"}]}, "dateRecorded": "2018-09-17", "сервер": {"программирование": [{"System": "http://snomed.info/sct"; "код": "24484000"; "вывод": "серьезный"}]}}}]}</span><span class="sxs-lookup"><span data-stu-id="ac135-199">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="ac135-200">Дополнительные [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="ac135-200">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="ac135-201">Происходит</span><span class="sxs-lookup"><span data-stu-id="ac135-201">Encounter</span></span>

<span data-ttu-id="ac135-202">Это минимальные обязательные поля, которые являются подмножеством подмножества для основного профиля в США, которое должно иметь следующие поля:</span><span class="sxs-lookup"><span data-stu-id="ac135-202">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

1. <span data-ttu-id="ac135-203">Состояни</span><span class="sxs-lookup"><span data-stu-id="ac135-203">Status</span></span>
2. <span data-ttu-id="ac135-204">Введите [0]. Кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="ac135-204">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="ac135-205">Кроме того, ниже перечислены поля, которые можно получить из основного приложения US "требуется поддержка".</span><span class="sxs-lookup"><span data-stu-id="ac135-205">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

1. <span data-ttu-id="ac135-206">Period. Start</span><span class="sxs-lookup"><span data-stu-id="ac135-206">Period.Start</span></span>
2. <span data-ttu-id="ac135-207">Расположение [0]. Расположение. Display</span><span class="sxs-lookup"><span data-stu-id="ac135-207">Location[0].Location.Display</span></span>

<span data-ttu-id="ac135-208">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="ac135-208">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="ac135-209">пациент =\<patient ID></span><span class="sxs-lookup"><span data-stu-id="ac135-209">patient=\<patient id></span></span>
2. <span data-ttu-id="ac135-210">_sort: DESC =\<Field ex.</span><span class="sxs-lookup"><span data-stu-id="ac135-210">_sort:desc=\<field ex.</span></span> <span data-ttu-id="ac135-211">Дата></span><span class="sxs-lookup"><span data-stu-id="ac135-211">date></span></span>
3. <span data-ttu-id="ac135-212">_count =\<максимальное число результатов></span><span class="sxs-lookup"><span data-stu-id="ac135-212">_count=\<max results></span></span>

<span data-ttu-id="ac135-213">Цель — получить Последнее известное расположение пациента.</span><span class="sxs-lookup"><span data-stu-id="ac135-213">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="ac135-214">Каждый из этих обнаружений ссылается на ресурс расположения.</span><span class="sxs-lookup"><span data-stu-id="ac135-214">Each encounter references a location resource.</span></span> <span data-ttu-id="ac135-215">Ссылка также должна включать поле отображения местоположения.</span><span class="sxs-lookup"><span data-stu-id="ac135-215">The reference shall also include the location's display field.</span></span> <span data-ttu-id="ac135-216">Ниже приведен пример этого звонка.</span><span class="sxs-lookup"><span data-stu-id="ac135-216">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="ac135-217">Запрос: GET <fhir-Server>/Encounter? пациент =<пациент-ID>&_sort:d ESC = Дата&_count = 1</span><span class="sxs-lookup"><span data-stu-id="ac135-217">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="ac135-218">Ответ: {"ResourceType": "комплект", "тип": "набор результатов поиска", "всего": 1, "элемент": [{"ресурс": {"ИД": "Поиск", "идентификатор"-"<ресурсов>"; "идентификатор": [{"use": "официальный", "значение":<id>"состояние": "поступило"; "тип": [{"код": [{"Display": "Встреча"}],}], "пациент": {"ссылка": "пациент/<пациент-ID"> "};" период ": {" начало ":" 09/17/2018 1:00:00 PM "}," расположение ": [{" расположение ": {" Display ":" курс-корпоративный "},}]}}]}</span><span class="sxs-lookup"><span data-stu-id="ac135-218">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="ac135-219">Дополнительные [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="ac135-219">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="ac135-220">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="ac135-220">AllergyIntolerance</span></span>

<span data-ttu-id="ac135-221">Это минимальные обязательные поля, которые являются подмножеством профиля Argonaut AllergyIntolerance:</span><span class="sxs-lookup"><span data-stu-id="ac135-221">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="ac135-222">Code. Text</span><span class="sxs-lookup"><span data-stu-id="ac135-222">Code.Text</span></span>
2. <span data-ttu-id="ac135-223">Код. кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="ac135-223">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="ac135-224">Состояни</span><span class="sxs-lookup"><span data-stu-id="ac135-224">Status</span></span>

<span data-ttu-id="ac135-225">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также считывает следующие поля:</span><span class="sxs-lookup"><span data-stu-id="ac135-225">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="ac135-226">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="ac135-226">RecordedDate</span></span>
2. <span data-ttu-id="ac135-227">Примечание. текст</span><span class="sxs-lookup"><span data-stu-id="ac135-227">Note.Text</span></span>
3. <span data-ttu-id="ac135-228">Реакция [..]. Вещество. текст</span><span class="sxs-lookup"><span data-stu-id="ac135-228">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="ac135-229">Реакция [..]. Манифест [..]. Текстовые</span><span class="sxs-lookup"><span data-stu-id="ac135-229">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="ac135-230">Text. Div</span><span class="sxs-lookup"><span data-stu-id="ac135-230">Text.Div</span></span>

<span data-ttu-id="ac135-231">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="ac135-231">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="ac135-232">Пациент = \<patient ID></span><span class="sxs-lookup"><span data-stu-id="ac135-232">Patient =  \<patient id></span></span>

<span data-ttu-id="ac135-233">Ниже приведен пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="ac135-233">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="ac135-234">Запрос: GET <fhir-Server>/AllergyIntolerance? пациент =<пациент-ID></span><span class="sxs-lookup"><span data-stu-id="ac135-234">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="ac135-235">Response: {"resourceType": "набор", "идентификатор <": "пакет-ID>", "тип": "набор поиска", "всего", "элемент": [{"ресурс": {"resourceType": "AllergyIntolerance", "идентификатор": "<Resource-id>", "recordedDate": "2018-09-17T07:00:00.000 Z", "веществ": {"текст": "Cashew" "}", "состояние": "подтверждено", "реакция": [{"вещество". ": {" текст ":" Cashew Гайк allergenic извлечь введенный продукт "}," проявление ": [{" текст ":" реакция на Anaphylactic "}]}</span><span class="sxs-lookup"><span data-stu-id="ac135-235">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="ac135-236">Дополнительные [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="ac135-236">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="ac135-237">Лечения заказ</span><span class="sxs-lookup"><span data-stu-id="ac135-237">Medication Order</span></span>

<span data-ttu-id="ac135-238">Это минимальные обязательные поля, которые являются подмножеством профиля Argonaut MedicationOrder:</span><span class="sxs-lookup"><span data-stu-id="ac135-238">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="ac135-239">DateWritten</span><span class="sxs-lookup"><span data-stu-id="ac135-239">DateWritten</span></span>
2. <span data-ttu-id="ac135-240">Предписанный. Display</span><span class="sxs-lookup"><span data-stu-id="ac135-240">Prescriber.Display</span></span>
3. <span data-ttu-id="ac135-241">Лечения. Display (если ссылка)</span><span class="sxs-lookup"><span data-stu-id="ac135-241">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="ac135-242">Лечения. Text (если понятие)</span><span class="sxs-lookup"><span data-stu-id="ac135-242">Medication.Text (if concept)</span></span>

<span data-ttu-id="ac135-243">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="ac135-243">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="ac135-244">DateEnded</span><span class="sxs-lookup"><span data-stu-id="ac135-244">DateEnded</span></span>
2. <span data-ttu-id="ac135-245">DosageInstruction. Text</span><span class="sxs-lookup"><span data-stu-id="ac135-245">DosageInstruction.Text</span></span>
3. <span data-ttu-id="ac135-246">Text. Div</span><span class="sxs-lookup"><span data-stu-id="ac135-246">Text.Div</span></span>

<span data-ttu-id="ac135-247">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="ac135-247">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="ac135-248">пациент =\<patient ID></span><span class="sxs-lookup"><span data-stu-id="ac135-248">patient=\<patient id></span></span>
2. <span data-ttu-id="ac135-249">_count =\<максимальное число результатов></span><span class="sxs-lookup"><span data-stu-id="ac135-249">_count=\<max results></span></span>

<span data-ttu-id="ac135-250">Ниже приведен пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="ac135-250">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="ac135-251">Запрос: GET <fhir-Server>/MedicationOrder? пациент =<пациент-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="ac135-251">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="ac135-252">Response: {"resourceType": "пакет", "идентификатор <": "набор-ID>", "тип": "набор поиска", "всего": 1, "запись": [{"ресурс": {"resourceType": "MedicationOrder", "идентификатор": "<ресурс-идентификатор>"; "dateWritten": "," medicationCodeableConcept ": {", ":" Lisinopril 20 mg устные Планшет "}," предназначается ": {" вывод ":" Джейн Петров "}," dosageInstruction ": [{" текст ":" 2018-09-17</span><span class="sxs-lookup"><span data-stu-id="ac135-252">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="ac135-253">Дополнительные [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="ac135-253">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="ac135-254">Приложения</span><span class="sxs-lookup"><span data-stu-id="ac135-254">Coverage</span></span>

<span data-ttu-id="ac135-255">Это минимальный обязательный набор полей, не охваченных профилями США или Argonaut:</span><span class="sxs-lookup"><span data-stu-id="ac135-255">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="ac135-256">Payor</span><span class="sxs-lookup"><span data-stu-id="ac135-256">Payor</span></span>

<span data-ttu-id="ac135-257">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="ac135-257">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="ac135-258">пациент =\<patient ID></span><span class="sxs-lookup"><span data-stu-id="ac135-258">patient=\<patient id></span></span>

<span data-ttu-id="ac135-259">Ниже приведен пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="ac135-259">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="ac135-260">Запрос: GET <fhir-Server>/Coverage? пациент =<пациент-ID></span><span class="sxs-lookup"><span data-stu-id="ac135-260">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="ac135-261">Ответ: {"resourceType": "пакет", "тип": "функция поиска", "Итого": 1, "запись": [{"ресурс": {"resourceType": "Coverage", "план": "без основного страхового обеспечения", "> <подписчик": "нет на месте", "на"> <</span><span class="sxs-lookup"><span data-stu-id="ac135-261">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="ac135-262">Дополнительные [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="ac135-262">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="ac135-263">Местоположение</span><span class="sxs-lookup"><span data-stu-id="ac135-263">Location</span></span>

<span data-ttu-id="ac135-264">Этот ресурс используется только в качестве ссылки на ресурс " [встреча](#encounter) ".</span><span class="sxs-lookup"><span data-stu-id="ac135-264">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="ac135-265">Дополнительные [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="ac135-265">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
