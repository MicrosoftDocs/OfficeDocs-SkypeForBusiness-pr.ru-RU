---
title: Интерфейс DSTU2 пациентов для приложений и ехр интеграции
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
description: Интеграция приложений Microsoft Teams пациентов ехр
ms.openlocfilehash: 10a6b21e583b5fdd3e70857c4cfc5e7e21a7e988
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153821"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="2175a-103">Характеристики интерфейса DSTU2</span><span class="sxs-lookup"><span data-stu-id="2175a-103">DSTU2 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="2175a-104">Настройка или перенастройка сервера ФХИР для работы с приложением Microsoft Teams пациентов требует понимания данных, к которым приложению требуется доступ.</span><span class="sxs-lookup"><span data-stu-id="2175a-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="2175a-105">Сервер ФХИР должен поддерживать запросы POST, используя пакеты для указанных ниже ресурсов.</span><span class="sxs-lookup"><span data-stu-id="2175a-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="2175a-106">Подождите</span><span class="sxs-lookup"><span data-stu-id="2175a-106">Patient</span></span>](#patient)
- [<span data-ttu-id="2175a-107">Наблюдение</span><span class="sxs-lookup"><span data-stu-id="2175a-107">Observation</span></span>](#observation)
- [<span data-ttu-id="2175a-108">Условие</span><span class="sxs-lookup"><span data-stu-id="2175a-108">Condition</span></span>](#condition)
- [<span data-ttu-id="2175a-109">Происходит</span><span class="sxs-lookup"><span data-stu-id="2175a-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="2175a-110">Недопустимый аллерги</span><span class="sxs-lookup"><span data-stu-id="2175a-110">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="2175a-111">Приложения</span><span class="sxs-lookup"><span data-stu-id="2175a-111">Coverage</span></span>](#coverage)
- [<span data-ttu-id="2175a-112">Лечения заказ</span><span class="sxs-lookup"><span data-stu-id="2175a-112">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="2175a-113">Расположение</span><span class="sxs-lookup"><span data-stu-id="2175a-113">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="2175a-114">Ресурс пациент является единственным обязательным ресурсом (без которого приложение не будет загружаться вообще).</span><span class="sxs-lookup"><span data-stu-id="2175a-114">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="2175a-115">Тем не менее, рекомендуется, чтобы партнеры реализовали поддержку всех вышеупомянутых ресурсов для спецификаций, указанных ниже, для наилучшего взаимодействия с пользователем в приложении Microsoft Teams пациентов.</span><span class="sxs-lookup"><span data-stu-id="2175a-115">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="2175a-116">Запросы из приложения Microsoft Teams пациентов для нескольких ресурсов. отправляет набор (пакет) запросов на URL-адрес сервера ФХИР.</span><span class="sxs-lookup"><span data-stu-id="2175a-116">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="2175a-117">Сервер обрабатывает каждый запрос и возвращает набор ресурсов, соответствующих каждому запросу.</span><span class="sxs-lookup"><span data-stu-id="2175a-117">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="2175a-118">Дополнительные сведения и примеры можно найти в [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction)разделе.</span><span class="sxs-lookup"><span data-stu-id="2175a-118">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="2175a-119">Все перечисленные ниже ресурсы ФХИР должны быть доступны по прямой ссылке на ресурс.</span><span class="sxs-lookup"><span data-stu-id="2175a-119">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="2175a-120">Минимальный набор полей, необходимый для установки соответствия</span><span class="sxs-lookup"><span data-stu-id="2175a-120">Conformance minimum required field set</span></span>

 <span data-ttu-id="2175a-121">Сервер ФХИР должен реализовать инструкцию соответствия, чтобы получить сводную информацию о ее возможностях фактуал.</span><span class="sxs-lookup"><span data-stu-id="2175a-121">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="2175a-122">Ниже перечислены параметры на сервере DSTU2 ФХИР:</span><span class="sxs-lookup"><span data-stu-id="2175a-122">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="2175a-123">ДЕРЖИВАЕТ</span><span class="sxs-lookup"><span data-stu-id="2175a-123">REST</span></span>
   1. <span data-ttu-id="2175a-124">Режиме</span><span class="sxs-lookup"><span data-stu-id="2175a-124">Mode</span></span>
   2. <span data-ttu-id="2175a-125">Действует</span><span class="sxs-lookup"><span data-stu-id="2175a-125">Interaction</span></span>
   3. <span data-ttu-id="2175a-126">Ресурс: тип</span><span class="sxs-lookup"><span data-stu-id="2175a-126">Resource: Type</span></span>
   4. <span data-ttu-id="2175a-127">Безопасность: [расширение URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="2175a-127">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="2175a-128">Фхирверсион (для нашего кода требуется, чтобы узнать, в какую версию следует поворачивать, так как мы поддерживаем несколько версий.)</span><span class="sxs-lookup"><span data-stu-id="2175a-128">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="2175a-129">Дополнительные [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="2175a-129">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="2175a-130">Подождите</span><span class="sxs-lookup"><span data-stu-id="2175a-130">Patient</span></span>

<span data-ttu-id="2175a-131">Это минимальные обязательные поля, которые являются подмножеством полей [профиля пациента аргонаут](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :</span><span class="sxs-lookup"><span data-stu-id="2175a-131">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="2175a-132">Family (имя)</span><span class="sxs-lookup"><span data-stu-id="2175a-132">Name.Family</span></span>
2. <span data-ttu-id="2175a-133">Name (имя). задано</span><span class="sxs-lookup"><span data-stu-id="2175a-133">Name.Given</span></span>
3. <span data-ttu-id="2175a-134">Полу</span><span class="sxs-lookup"><span data-stu-id="2175a-134">Gender</span></span>
4. <span data-ttu-id="2175a-135">Рождения</span><span class="sxs-lookup"><span data-stu-id="2175a-135">BirthDate</span></span>
5. <span data-ttu-id="2175a-136">МРН (идентификатор)</span><span class="sxs-lookup"><span data-stu-id="2175a-136">MRN (Identifier)</span></span>

<span data-ttu-id="2175a-137">В дополнение к полям Аргонаут для удобства пользователей приложение пациентов также считывает следующие поля:</span><span class="sxs-lookup"><span data-stu-id="2175a-137">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="2175a-138">Name. use</span><span class="sxs-lookup"><span data-stu-id="2175a-138">Name.Use</span></span>
2. <span data-ttu-id="2175a-139">Name. prefix</span><span class="sxs-lookup"><span data-stu-id="2175a-139">Name.Prefix</span></span>
3. <span data-ttu-id="2175a-140">Карепровидер (эта ссылка на ресурс пациент должна содержать отображаемые поля, показанные в приведенном ниже примере).</span><span class="sxs-lookup"><span data-stu-id="2175a-140">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="2175a-141">Запрос: получение <фхир-Server>/патиент/<пациент-ID></span><span class="sxs-lookup"><span data-stu-id="2175a-141">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="2175a-142">Ответ: {"resourceType": "Patient", "идентификатор": "<пациент-ID>";.</span><span class="sxs-lookup"><span data-stu-id="2175a-142">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="2175a-143">.</span><span class="sxs-lookup"><span data-stu-id="2175a-143">.</span></span>
      <span data-ttu-id="2175a-144">.</span><span class="sxs-lookup"><span data-stu-id="2175a-144">.</span></span>
      <span data-ttu-id="2175a-145">"имя": [{"use": "официальный", "префикс": ["MR"], "Family": ["Хугх"] "," ". [" Чау "]}]," идентификатор ": [{" использование ":" официальный "," тип ": {" программирование ": [{" System ":"https://hl7.org/fhir/v2/0203";" код ":" MR "}]};" значение ":" м ";" Карепровидер ": [{" Display ":" Джейн Петров "}],} 1234567 1957-06-05</span><span class="sxs-lookup"><span data-stu-id="2175a-145">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="2175a-146">Поиск ресурсов использует метод POST по адресу/патиент/_search и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="2175a-146">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="2175a-147">номер</span><span class="sxs-lookup"><span data-stu-id="2175a-147">id</span></span>
2. <span data-ttu-id="2175a-148">Семья: Contains = (ищет все пациентов, чье имя семейства оно содержат.)</span><span class="sxs-lookup"><span data-stu-id="2175a-148">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="2175a-149">заданный\<= подстрока></span><span class="sxs-lookup"><span data-stu-id="2175a-149">given=\<substring></span></span>
4. <span data-ttu-id="2175a-150">Name =\<substring></span><span class="sxs-lookup"><span data-stu-id="2175a-150">name=\<substring></span></span>
5. <span data-ttu-id="2175a-151">Дата рождения = (точное совпадение)</span><span class="sxs-lookup"><span data-stu-id="2175a-151">birthdate=(exact match)</span></span>
6. <span data-ttu-id="2175a-152">\_Count (максимальное количество возвращаемых результатов)</span><span class="sxs-lookup"><span data-stu-id="2175a-152">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="2175a-153">Ответ должен содержать общее количество записей, возвращенных в результате поиска, и \_количество будет использоваться патиентсапп для ограничения количества возвращенных записей.</span><span class="sxs-lookup"><span data-stu-id="2175a-153">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="2175a-154">Идентификатор =\<МРН></span><span class="sxs-lookup"><span data-stu-id="2175a-154">identifier=\<mrn></span></span>

<span data-ttu-id="2175a-155">Цель — найти и отфильтровать пациента в пациент, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2175a-155">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="2175a-156">ID: это идентификатор ресурса, который содержит каждый ресурс в ФХИР.</span><span class="sxs-lookup"><span data-stu-id="2175a-156">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="2175a-157">МРН: фактический идентификатор пациента, который будет знать клиникал сотрудника.</span><span class="sxs-lookup"><span data-stu-id="2175a-157">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="2175a-158">Мы понимаем, что этот МРН основывается на типе идентификатора в ресурсе идентификатора в ФХИР</span><span class="sxs-lookup"><span data-stu-id="2175a-158">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="2175a-159">Имя</span><span class="sxs-lookup"><span data-stu-id="2175a-159">Name</span></span>
- <span data-ttu-id="2175a-160">Рождения</span><span class="sxs-lookup"><span data-stu-id="2175a-160">Birthdate</span></span>

<span data-ttu-id="2175a-161">Ниже приведен пример этого звонка.</span><span class="sxs-lookup"><span data-stu-id="2175a-161">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="2175a-162">Запрос: POST <фхир-Server>/патиент/_search запроса: с указанным = хугх&Family = Чау</span><span class="sxs-lookup"><span data-stu-id="2175a-162">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="2175a-163">Response: {"resourceType": "пакет", "идентификатор": "<-ID пакета>".</span><span class="sxs-lookup"><span data-stu-id="2175a-163">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="2175a-164">.</span><span class="sxs-lookup"><span data-stu-id="2175a-164">.</span></span>
      <span data-ttu-id="2175a-165">.</span><span class="sxs-lookup"><span data-stu-id="2175a-165">.</span></span>
      <span data-ttu-id="2175a-166">"Entry": [{"ресурс": {"resourceType": "пациент"; "идентификатор": "<пациент-ID>", "имя": [{"текст": "Хугх Чау", "семья": ["Чау"], ""--"," Дата ":" м ":"----------"1957-06-05</span><span class="sxs-lookup"><span data-stu-id="2175a-166">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="2175a-167">Дополнительные [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="2175a-167">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="2175a-168">Наблюдение</span><span class="sxs-lookup"><span data-stu-id="2175a-168">Observation</span></span>

<span data-ttu-id="2175a-169">Это минимальные обязательные поля, которые являются подмножеством профиля Аргонаут важную подпись:</span><span class="sxs-lookup"><span data-stu-id="2175a-169">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="2175a-170">Эффективная (Дата и время)</span><span class="sxs-lookup"><span data-stu-id="2175a-170">Effective (date time or period)</span></span>
 2. <span data-ttu-id="2175a-171">Код. кодирование. Code</span><span class="sxs-lookup"><span data-stu-id="2175a-171">Code.Coding.Code</span></span>
 3. <span data-ttu-id="2175a-172">Валуекуантити. Value</span><span class="sxs-lookup"><span data-stu-id="2175a-172">ValueQuantity.Value</span></span>

<span data-ttu-id="2175a-173">В дополнение к полям Аргонаут для удобства пользователей приложение пациентов также считывает следующие поля:</span><span class="sxs-lookup"><span data-stu-id="2175a-173">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="2175a-174">Код. программирование. Display</span><span class="sxs-lookup"><span data-stu-id="2175a-174">Code.Coding.Display</span></span>
 2. <span data-ttu-id="2175a-175">Валуекуантити. ед.</span><span class="sxs-lookup"><span data-stu-id="2175a-175">ValueQuantity.Unit</span></span>

<span data-ttu-id="2175a-176">При использовании наблюдения за компонентами одна и та же логика применяется для наблюдения за каждым компонентом.</span><span class="sxs-lookup"><span data-stu-id="2175a-176">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="2175a-177">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="2175a-177">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="2175a-178">пациент =\<ИД пациента\></span><span class="sxs-lookup"><span data-stu-id="2175a-178">patient=\<patient id\></span></span>
2. <span data-ttu-id="2175a-179">Sort: DESC =\<поле ex.</span><span class="sxs-lookup"><span data-stu-id="2175a-179">sort:desc=\<field ex.</span></span> <span data-ttu-id="2175a-180">окончания\></span><span class="sxs-lookup"><span data-stu-id="2175a-180">date\></span></span>

<span data-ttu-id="2175a-181">Цель состоит в том, чтобы получить последние важные знаки для пациента, [Виталсигнс. ДСТУ. САЗ] (наблюдение?).</span><span class="sxs-lookup"><span data-stu-id="2175a-181">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="2175a-182">Запрос: GET <фхир-Server>/Обсерватион? пациент =<пациент-ID>&_sort:d ESC = Дата&Category = важные-признаки</span><span class="sxs-lookup"><span data-stu-id="2175a-182">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="2175a-183">Response: {"resourceType": "пакет", "идентификатор": <"пакет-ID>", "введите": ",", "," Итого ": 20," Entry ": [{" ресурс ": {" resourceType ":" наблюдение "," идентификатор ":" <ресурс-идентификатор> ";" Категория ": {" программирование ": [{code": "важные-знаки"}],}, "код": {"программирование": [{"Systemhttp://loinc.org": ""; "код": "39156-5", "Display": "БМИ"}],}, "еффективедатетиме": "2009-12-01"; "валуекуантити": {"значение": 34,4; "единица": "кг/m2", "http://unitsofmeasure.orgсистема": "кг/m2"}},},.</span><span class="sxs-lookup"><span data-stu-id="2175a-183">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="2175a-184">.</span><span class="sxs-lookup"><span data-stu-id="2175a-184">.</span></span>
        <span data-ttu-id="2175a-185">.</span><span class="sxs-lookup"><span data-stu-id="2175a-185">.</span></span>
      <span data-ttu-id="2175a-186">] }</span><span class="sxs-lookup"><span data-stu-id="2175a-186">] }</span></span>

* * *

<span data-ttu-id="2175a-187">Дополнительные [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="2175a-187">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="2175a-188">Условие</span><span class="sxs-lookup"><span data-stu-id="2175a-188">Condition</span></span>

<span data-ttu-id="2175a-189">Это минимальные обязательные поля, которые являются подмножеством [профиля условия аргонаут](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="2175a-189">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="2175a-190">Код. кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="2175a-190">Code.Coding[0].Display</span></span>

<span data-ttu-id="2175a-191">В дополнение к полям Аргонаут для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="2175a-191">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="2175a-192">Дата записи</span><span class="sxs-lookup"><span data-stu-id="2175a-192">Date Recorded</span></span>
2. <span data-ttu-id="2175a-193">Уровню серьезности</span><span class="sxs-lookup"><span data-stu-id="2175a-193">Severity</span></span>

<span data-ttu-id="2175a-194">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="2175a-194">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="2175a-195">пациент =\<patient ID></span><span class="sxs-lookup"><span data-stu-id="2175a-195">patient=\<patient id></span></span>
2. <span data-ttu-id="2175a-196">_count =\<максимальное число результатов></span><span class="sxs-lookup"><span data-stu-id="2175a-196">_count=\<max results></span></span>

<span data-ttu-id="2175a-197">Ниже приведен пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="2175a-197">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="2175a-198">Запрос: GET <фхир-Server>/Кондитион? пациент =<пациент-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="2175a-198">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="2175a-199">Response: {"resourceType": "пакет", "идентификатор <": "набор-ID>", "тип": "набор поиска", "всего": 1, "запись": [{"ресурс": {"resourceType": "условие", "идентификатор": "<ресурс-ID>", "код": {",http://snomed.info/sctкод": ",", ",", "," неуропаси (нерве) "}]}," датерекордед ":" 2018-09-17 "," важность ": {" программирование ": [386033004 EM ":"http://snomed.info/sct, "код": "24484000", "Display": "серьезный"}]}},}]}</span><span class="sxs-lookup"><span data-stu-id="2175a-199">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="2175a-200">Дополнительные [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="2175a-200">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="2175a-201">Происходит</span><span class="sxs-lookup"><span data-stu-id="2175a-201">Encounter</span></span>

<span data-ttu-id="2175a-202">Это минимальные обязательные поля, которые являются подмножеством подмножества для основного профиля в США, которое должно иметь следующие поля:</span><span class="sxs-lookup"><span data-stu-id="2175a-202">These are the minimum required fields, which are a subset of the US Core Encounter profile “must have” fields:</span></span>

1. <span data-ttu-id="2175a-203">Состояни</span><span class="sxs-lookup"><span data-stu-id="2175a-203">Status</span></span>
2. <span data-ttu-id="2175a-204">Введите [0]. Кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="2175a-204">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="2175a-205">Кроме того, ниже перечислены поля, которые можно получить из основного приложения US "требуется поддержка".</span><span class="sxs-lookup"><span data-stu-id="2175a-205">In addition, the following fields from US Core Encounter profile’s “must support” fields</span></span>

1. <span data-ttu-id="2175a-206">Period. Start</span><span class="sxs-lookup"><span data-stu-id="2175a-206">Period.Start</span></span>
2. <span data-ttu-id="2175a-207">Расположение [0]. Расположение. Display</span><span class="sxs-lookup"><span data-stu-id="2175a-207">Location[0].Location.Display</span></span>

<span data-ttu-id="2175a-208">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="2175a-208">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="2175a-209">пациент =\<patient ID></span><span class="sxs-lookup"><span data-stu-id="2175a-209">patient=\<patient id></span></span>
2. <span data-ttu-id="2175a-210">_sort: DESC =\<Field ex.</span><span class="sxs-lookup"><span data-stu-id="2175a-210">_sort:desc=\<field ex.</span></span> <span data-ttu-id="2175a-211">Дата></span><span class="sxs-lookup"><span data-stu-id="2175a-211">date></span></span>
3. <span data-ttu-id="2175a-212">_count =\<максимальное число результатов></span><span class="sxs-lookup"><span data-stu-id="2175a-212">_count=\<max results></span></span>

<span data-ttu-id="2175a-213">Цель — получить Последнее известное расположение пациента.</span><span class="sxs-lookup"><span data-stu-id="2175a-213">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="2175a-214">Каждый из этих обнаружений ссылается на ресурс расположения.</span><span class="sxs-lookup"><span data-stu-id="2175a-214">Each encounter references a location resource.</span></span> <span data-ttu-id="2175a-215">Ссылка также должна включать поле отображения местоположения.</span><span class="sxs-lookup"><span data-stu-id="2175a-215">The reference shall also include the location’s display field.</span></span> <span data-ttu-id="2175a-216">Ниже приведен пример этого звонка.</span><span class="sxs-lookup"><span data-stu-id="2175a-216">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="2175a-217">Запрос: GET <фхир-Server>/Енкаунтер? пациент =<пациент-ID>&_sort:d ESC = Дата&_count = 1</span><span class="sxs-lookup"><span data-stu-id="2175a-217">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="2175a-218">Response: {"ResourceType": "пакет", "тип": "набор поиска", "Итого": {"ИД> <": "Поиск": {",", ",", "идентификатор": [{":", ",", "<id>"}]; "состояние": "доставлено", "тип": [{"код", "Встреча", "время", "Patient": {"ссылка": "пациент/<пациент-ID>"}, "period": {"Start": "09/17/2018 1:00:00 PM"}, "расположение": [{              "расположение": {"Display": "курс-корпоративный"},}]}}]}</span><span class="sxs-lookup"><span data-stu-id="2175a-218">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="2175a-219">Дополнительные [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="2175a-219">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="2175a-220">аллергинтолеранце</span><span class="sxs-lookup"><span data-stu-id="2175a-220">AllergyIntolerance</span></span>

<span data-ttu-id="2175a-221">Это минимальные обязательные поля, которые являются подмножеством профиля Аргонаут Аллергинтолеранце:</span><span class="sxs-lookup"><span data-stu-id="2175a-221">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="2175a-222">Code. Text</span><span class="sxs-lookup"><span data-stu-id="2175a-222">Code.Text</span></span>
2. <span data-ttu-id="2175a-223">Код. кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="2175a-223">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="2175a-224">Состояни</span><span class="sxs-lookup"><span data-stu-id="2175a-224">Status</span></span>

<span data-ttu-id="2175a-225">В дополнение к полям Аргонаут для удобства пользователей приложение пациентов также считывает следующие поля:</span><span class="sxs-lookup"><span data-stu-id="2175a-225">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="2175a-226">рекордеддате</span><span class="sxs-lookup"><span data-stu-id="2175a-226">RecordedDate</span></span>
2. <span data-ttu-id="2175a-227">Примечание. текст</span><span class="sxs-lookup"><span data-stu-id="2175a-227">Note.Text</span></span>
3. <span data-ttu-id="2175a-228">Реакция [..]. Вещество. текст</span><span class="sxs-lookup"><span data-stu-id="2175a-228">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="2175a-229">Реакция [..]. Манифест [..]. Текстовые</span><span class="sxs-lookup"><span data-stu-id="2175a-229">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="2175a-230">Text. Div</span><span class="sxs-lookup"><span data-stu-id="2175a-230">Text.Div</span></span>

<span data-ttu-id="2175a-231">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="2175a-231">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="2175a-232">Пациент = \<patient ID></span><span class="sxs-lookup"><span data-stu-id="2175a-232">Patient =  \<patient id></span></span>

<span data-ttu-id="2175a-233">Ниже приведен пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="2175a-233">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="2175a-234">Запрос: GET <фхир-Server>/Аллергинтолеранце? пациент =<пациент-ID></span><span class="sxs-lookup"><span data-stu-id="2175a-234">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="2175a-235">Response: {"resourceType": "пучок", "идентификатор <": "пакет-ID>", "тип": "набор поиска", "всего": 1, "запись": [{"ресурс": {"resourceType": "Аллергинтолеранце"; "идентификатор": "<Resource-id>", "Рекордеддате": "2018-09-17T07:00:00.000 Z"; "состояние": "подтверждено", "реакция": [{"марка": {"" тип ":" на ") [{" " On ": [{" текст ":" Анафилактикная реакция "}]}]}}]}</span><span class="sxs-lookup"><span data-stu-id="2175a-235">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="2175a-236">Дополнительные [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="2175a-236">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="2175a-237">Лечения заказ</span><span class="sxs-lookup"><span data-stu-id="2175a-237">Medication Order</span></span>

<span data-ttu-id="2175a-238">Это минимальные обязательные поля, которые являются подмножеством профиля Аргонаут Медикатионордер:</span><span class="sxs-lookup"><span data-stu-id="2175a-238">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="2175a-239">датевриттен</span><span class="sxs-lookup"><span data-stu-id="2175a-239">DateWritten</span></span>
2. <span data-ttu-id="2175a-240">Предписанный. Display</span><span class="sxs-lookup"><span data-stu-id="2175a-240">Prescriber.Display</span></span>
3. <span data-ttu-id="2175a-241">Лечения. Display (если ссылка)</span><span class="sxs-lookup"><span data-stu-id="2175a-241">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="2175a-242">Лечения. Text (если понятие)</span><span class="sxs-lookup"><span data-stu-id="2175a-242">Medication.Text (if concept)</span></span>

<span data-ttu-id="2175a-243">В дополнение к полям Аргонаут для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="2175a-243">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="2175a-244">датиндед</span><span class="sxs-lookup"><span data-stu-id="2175a-244">DateEnded</span></span>
2. <span data-ttu-id="2175a-245">Досажеинструктион. Text</span><span class="sxs-lookup"><span data-stu-id="2175a-245">DosageInstruction.Text</span></span>
3. <span data-ttu-id="2175a-246">Text. Div</span><span class="sxs-lookup"><span data-stu-id="2175a-246">Text.Div</span></span>

<span data-ttu-id="2175a-247">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="2175a-247">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="2175a-248">пациент =\<patient ID></span><span class="sxs-lookup"><span data-stu-id="2175a-248">patient=\<patient id></span></span>
2. <span data-ttu-id="2175a-249">_count =\<максимальное число результатов></span><span class="sxs-lookup"><span data-stu-id="2175a-249">_count=\<max results></span></span>

<span data-ttu-id="2175a-250">Ниже приведен пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="2175a-250">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="2175a-251">Запрос: GET <фхир-Server>/Медикатионордер? пациент =<пациент-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="2175a-251">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="2175a-252">Response: {"resourceType": "пакет", "идентификатор <": "набор-ID>", "тип": "набор поиска", "всего": 1, "запись": [{"ресурс": {"resourceType": "Медикатионордер", "идентификатор": "<ресурс-идентификатор>"; "датевриттен": "," медикатионкодеаблеконцепт ": {", ":" лисиноприл 20 mg устные Планшет "}," предназначается ": {" вывод ":" Джейн Петров "}," досажеинструктион ": [{" текст ":" 2018-09-17</span><span class="sxs-lookup"><span data-stu-id="2175a-252">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="2175a-253">Дополнительные [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="2175a-253">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="2175a-254">Приложения</span><span class="sxs-lookup"><span data-stu-id="2175a-254">Coverage</span></span>

<span data-ttu-id="2175a-255">Это минимальный обязательный набор полей, не охваченных профилями США или Аргонаут:</span><span class="sxs-lookup"><span data-stu-id="2175a-255">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="2175a-256">пайор</span><span class="sxs-lookup"><span data-stu-id="2175a-256">Payor</span></span>

<span data-ttu-id="2175a-257">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="2175a-257">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="2175a-258">пациент =\<patient ID></span><span class="sxs-lookup"><span data-stu-id="2175a-258">patient=\<patient id></span></span>

<span data-ttu-id="2175a-259">Ниже приведен пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="2175a-259">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="2175a-260">Запрос: GET <фхир-Server>/Ковераже? пациент =<пациент-ID></span><span class="sxs-lookup"><span data-stu-id="2175a-260">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="2175a-261">Ответ: {"resourceType": "пакет", "тип": "функция поиска", "Итого": 1, "запись": [{"ресурс": {"resourceType": "Coverage", "план": "без основного страхового обеспечения", "> <подписчик": "нет на месте", "на"> <</span><span class="sxs-lookup"><span data-stu-id="2175a-261">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="2175a-262">Дополнительные [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="2175a-262">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="2175a-263">Местоположение</span><span class="sxs-lookup"><span data-stu-id="2175a-263">Location</span></span>

<span data-ttu-id="2175a-264">Этот ресурс используется только в качестве ссылки на ресурс " [встреча](#encounter) ".</span><span class="sxs-lookup"><span data-stu-id="2175a-264">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="2175a-265">Дополнительные [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="2175a-265">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
