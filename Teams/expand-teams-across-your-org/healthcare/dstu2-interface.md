---
title: " Приложение пациентов и EHR интеграции DSTU2 интерфейс"
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Интеграция EHR приложения пострадавших группами Майкрософт
ms.openlocfilehash: 85fd90fb338f8b19762dc9433fa1dc281f3cedff
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643126"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="4f6d3-103">Спецификации интерфейса DSTU2</span><span class="sxs-lookup"><span data-stu-id="4f6d3-103">DSTU2 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="4f6d3-104">Настройка или перенастройка сервер FHIR для работы с приложением Microsoft группами пострадавших необходимо понимание того, какие данные требуется доступ к приложению.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="4f6d3-105">FHIR сервер должен поддерживать запросы POST, с помощью пакета для со следующими ресурсами:</span><span class="sxs-lookup"><span data-stu-id="4f6d3-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="4f6d3-106">Пострадавший</span><span class="sxs-lookup"><span data-stu-id="4f6d3-106">Patient</span></span>](#patient)
- [<span data-ttu-id="4f6d3-107">Наблюдения</span><span class="sxs-lookup"><span data-stu-id="4f6d3-107">Observation</span></span>](#observation)
- [<span data-ttu-id="4f6d3-108">Условие</span><span class="sxs-lookup"><span data-stu-id="4f6d3-108">Condition</span></span>](#condition)
- [<span data-ttu-id="4f6d3-109">Встретиться</span><span class="sxs-lookup"><span data-stu-id="4f6d3-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="4f6d3-110">Intolerance аллергических реакций</span><span class="sxs-lookup"><span data-stu-id="4f6d3-110">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="4f6d3-111">Покрытия</span><span class="sxs-lookup"><span data-stu-id="4f6d3-111">Coverage</span></span>](#coverage)
- [<span data-ttu-id="4f6d3-112">Порядок лечения</span><span class="sxs-lookup"><span data-stu-id="4f6d3-112">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="4f6d3-113">Расположение</span><span class="sxs-lookup"><span data-stu-id="4f6d3-113">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="4f6d3-114">Пациента ресурсов — это единственная обязательная ресурсов, (без которой приложение не будет загружен вообще.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-114">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="4f6d3-115">Тем не менее рекомендуется, что партнера реализации поддержки выше ресурсов на спецификации представлены ниже для рекомендации для конечных пользователей с группами пострадавших Microsoft App.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-115">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="4f6d3-116">Запросы из приложения пострадавших группами Майкрософт для нескольких ресурсов Публикация пакета (пакет) запросов для URL-адрес сервера FHIR.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-116">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="4f6d3-117">Сервер обрабатывает каждого запроса и возвращает набор ресурсов, совпадающих с каждого запроса.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-117">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="4f6d3-118">Дополнительные сведения и примеры, в разделе [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span><span class="sxs-lookup"><span data-stu-id="4f6d3-118">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="4f6d3-119">Следующие ресурсы FHIR должен быть доступен с помощью ссылки на прямое ресурсов.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-119">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="4f6d3-120">Задайте о соответствии минимальным обязательное поле</span><span class="sxs-lookup"><span data-stu-id="4f6d3-120">Conformance minimum required field set</span></span>

 <span data-ttu-id="4f6d3-121">Сервер FHIR необходимо реализовать заявление о соответствии для нас иметь факты Сводка его возможности.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-121">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="4f6d3-122">Мы рассчитываем ниже параметров в сервере FHIR DSTU2:</span><span class="sxs-lookup"><span data-stu-id="4f6d3-122">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="4f6d3-123">REST</span><span class="sxs-lookup"><span data-stu-id="4f6d3-123">REST</span></span>
   1. <span data-ttu-id="4f6d3-124">Режим</span><span class="sxs-lookup"><span data-stu-id="4f6d3-124">Mode</span></span>
   2. <span data-ttu-id="4f6d3-125">Взаимодействие</span><span class="sxs-lookup"><span data-stu-id="4f6d3-125">Interaction</span></span>
   3. <span data-ttu-id="4f6d3-126">Ресурс: тип</span><span class="sxs-lookup"><span data-stu-id="4f6d3-126">Resource: Type</span></span>
   4. <span data-ttu-id="4f6d3-127">Безопасность: [расширения для URI OAuth](http://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="4f6d3-127">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="4f6d3-128">FhirVersion (код требует, чтобы она понять, какие версии, мы должны вводить несколько как мы поддерживают различные версии.)</span><span class="sxs-lookup"><span data-stu-id="4f6d3-128">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="4f6d3-129">Просмотреть [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) другие сведения в этом поле значение.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-129">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="4f6d3-130">Пострадавший</span><span class="sxs-lookup"><span data-stu-id="4f6d3-130">Patient</span></span>

<span data-ttu-id="4f6d3-131">Далее представлены минимальные обязательные поля, которые представляют собой подмножество полей [Argonaut пациента профилей](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :</span><span class="sxs-lookup"><span data-stu-id="4f6d3-131">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="4f6d3-132">Name.Family</span><span class="sxs-lookup"><span data-stu-id="4f6d3-132">Name.Family</span></span>
2. <span data-ttu-id="4f6d3-133">Name.Given</span><span class="sxs-lookup"><span data-stu-id="4f6d3-133">Name.Given</span></span>
3. <span data-ttu-id="4f6d3-134">Пол</span><span class="sxs-lookup"><span data-stu-id="4f6d3-134">Gender</span></span>
4. <span data-ttu-id="4f6d3-135">Дата рождения</span><span class="sxs-lookup"><span data-stu-id="4f6d3-135">BirthDate</span></span>
5. <span data-ttu-id="4f6d3-136">MRN (идентификатор)</span><span class="sxs-lookup"><span data-stu-id="4f6d3-136">MRN (Identifier)</span></span>

<span data-ttu-id="4f6d3-137">Помимо полей Argonaut для удобную работу пользователя приложения пострадавших также считывает следующие поля:</span><span class="sxs-lookup"><span data-stu-id="4f6d3-137">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="4f6d3-138">Name.Use</span><span class="sxs-lookup"><span data-stu-id="4f6d3-138">Name.Use</span></span>
2. <span data-ttu-id="4f6d3-139">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="4f6d3-139">Name.Prefix</span></span>
3. <span data-ttu-id="4f6d3-140">CareProvider (этой ссылки на пациента ресурса должна включать отображения полей, отображаемых в следующем примере).</span><span class="sxs-lookup"><span data-stu-id="4f6d3-140">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="4f6d3-141">Запрос: Получение <fhir-server>/пострадавший/<patient-id></span><span class="sxs-lookup"><span data-stu-id="4f6d3-141">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="4f6d3-142">Ответ: {«типа ресурса»: «Пациента», «id»: «<patient-id>».</span><span class="sxs-lookup"><span data-stu-id="4f6d3-142">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="4f6d3-143">.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-143"></span></span>
      <span data-ttu-id="4f6d3-144">.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-144"></span></span>
      <span data-ttu-id="4f6d3-145">«Имя»: [{«используйте»: «официальный», «префикс»: [«Mr»], «семья»: [«Chau»], «присвоенное»: [«Хью»]}], «идентификатор»: [{«используйте»: «официальный», «тип»: {«создание кода»: [{«система»: "http://hl7.org/fhir/v2/0203«, «код»: «MR»}]}, «значение»: «1234567»}], «Пол»: «штекер», «Дата рождения»: «1957-06-05 «, «careProvider»: [{«отображение»: «Иван Петров»}],}</span><span class="sxs-lookup"><span data-stu-id="4f6d3-145">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="4f6d3-146">Поиск ресурсов использует метод POST на /Patient/_search and следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="4f6d3-146">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="4f6d3-147">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="4f6d3-147">id</span></span>
2. <span data-ttu-id="4f6d3-148">Семейство: содержит = (выполняет поиск всех пострадавших семейства, имя которого содержит значение).</span><span class="sxs-lookup"><span data-stu-id="4f6d3-148">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="4f6d3-149">Данный =\<substring></span><span class="sxs-lookup"><span data-stu-id="4f6d3-149">given=\<substring></span></span>
4. <span data-ttu-id="4f6d3-150">имя =\<substring></span><span class="sxs-lookup"><span data-stu-id="4f6d3-150">name=\<substring></span></span>
5. <span data-ttu-id="4f6d3-151">Дата рождения =(exact match)</span><span class="sxs-lookup"><span data-stu-id="4f6d3-151">birthdate=(exact match)</span></span>
6. <span data-ttu-id="4f6d3-152">\_Count (максимальное количество результатов, которые должны быть возвращены)</span><span class="sxs-lookup"><span data-stu-id="4f6d3-152">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="4f6d3-153">Ответ должен содержать общее число записей, возвращаемых в результате поиска, и \_count будут использовать PatientsApp для ограничения числа возвращаемых записей.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-153">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="4f6d3-154">Идентификатор =\<mrn></span><span class="sxs-lookup"><span data-stu-id="4f6d3-154">identifier=\<mrn></span></span>

<span data-ttu-id="4f6d3-155">Цель — должны иметь возможность поиска и фильтров для пострадавший следующими службами:</span><span class="sxs-lookup"><span data-stu-id="4f6d3-155">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="4f6d3-156">ID — Это идентификатор ресурсов, у каждого ресурса FHIR.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-156">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="4f6d3-157">MRN: Это фактический идентификатор пациент, знать клинических персонала.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-157">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="4f6d3-158">Мы понимаем, это MRN, основанные на тип идентификатора внутри идентификатор ресурса в FHIR</span><span class="sxs-lookup"><span data-stu-id="4f6d3-158">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="4f6d3-159">Имя</span><span class="sxs-lookup"><span data-stu-id="4f6d3-159">Name</span></span>
- <span data-ttu-id="4f6d3-160">Дата рождения</span><span class="sxs-lookup"><span data-stu-id="4f6d3-160">Birthdate</span></span>

<span data-ttu-id="4f6d3-161">Следующий пример вызова см.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-161">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="4f6d3-162">Запрос: <fhir-server>/пострадавший/_search запросить запроса POST: заданного = hugh&family = chau</span><span class="sxs-lookup"><span data-stu-id="4f6d3-162">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="4f6d3-163">Ответ: {«типа ресурса»: «Объединяют», «id»: «<bundle-id>».</span><span class="sxs-lookup"><span data-stu-id="4f6d3-163">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="4f6d3-164">.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-164"></span></span>
      <span data-ttu-id="4f6d3-165">.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-165"></span></span>
      <span data-ttu-id="4f6d3-166">«запись»: [{«ресурс»: {«типа ресурса»: «Пациента», «id»: «<patient id>», «имя»: [{«текст»: «Хью Chau», «семья»: [«Chau»], «присвоенное»: [«Хью»]}], «Пол»: «штекер», «Дата рождения»: «1957-06-05»}, «поиск»: {«режима»: «match»}}]}</span><span class="sxs-lookup"><span data-stu-id="4f6d3-166">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="4f6d3-167">Просмотреть [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) другие сведения в этом поле значение.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-167">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="4f6d3-168">Наблюдения</span><span class="sxs-lookup"><span data-stu-id="4f6d3-168">Observation</span></span>

<span data-ttu-id="4f6d3-169">Далее представлены минимальные обязательные поля, которые представляют собой подмножество профилей Argonaut основные показатели:</span><span class="sxs-lookup"><span data-stu-id="4f6d3-169">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="4f6d3-170">Эффективного (дата, время или периода)</span><span class="sxs-lookup"><span data-stu-id="4f6d3-170">Effective (date time or period)</span></span>
 2. <span data-ttu-id="4f6d3-171">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="4f6d3-171">Code.Coding.Code</span></span>
 3. <span data-ttu-id="4f6d3-172">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="4f6d3-172">ValueQuantity.Value</span></span>

<span data-ttu-id="4f6d3-173">Помимо полей Argonaut для удобную работу пользователя приложения пострадавших также считывает следующие поля:</span><span class="sxs-lookup"><span data-stu-id="4f6d3-173">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="4f6d3-174">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="4f6d3-174">Code.Coding.Display</span></span>
 2. <span data-ttu-id="4f6d3-175">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="4f6d3-175">ValueQuantity.Unit</span></span>

<span data-ttu-id="4f6d3-176">Если используется компонент наблюдения, ту же логику применяется для каждого компонента наблюдения.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-176">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="4f6d3-177">Поиск ресурсов используется метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="4f6d3-177">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4f6d3-178">пострадавший =\<пациента идентификатор\></span><span class="sxs-lookup"><span data-stu-id="4f6d3-178">patient=\<patient id\></span></span>
2. <span data-ttu-id="4f6d3-179">Сортировка: desc =\<поля ex.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-179">sort:desc=\<field ex.</span></span> <span data-ttu-id="4f6d3-180">Дата\></span><span class="sxs-lookup"><span data-stu-id="4f6d3-180">date\></span></span>

<span data-ttu-id="4f6d3-181">Цель — должны иметь возможность получать последние основные показатели для пациентом [VitalSigns.DSTU.saz] (наблюдения?).</span><span class="sxs-lookup"><span data-stu-id="4f6d3-181">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="4f6d3-182">Запрос: Получение <fhir-server>/наблюдения? пострадавший = <patient-id>&_sort:desc = date&category = важной знаки</span><span class="sxs-lookup"><span data-stu-id="4f6d3-182">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="4f6d3-183">Ответ: {«типа ресурса»: «Объединяют», «id»: «<bundle id>», «тип»: «searchset», «общее»: 20, «запись»: [{«ресурс»: {«типа ресурса»: «Наблюдение», «id»: «<resource id>», «Категория»: {«создание кода»: [{код»: «важной знаки»}],}, «код»: {« Создание кода»: [{«система»: "http://loinc.org«, «код»: «39156-5», «отображение»: «массы»}],}, «effectiveDateTime»: «2009 г. — 12-01», «valueQuantity»: {«значение»: 34.4, «единицы»: «кг/m2», «система»:"http://unitsofmeasure.org«, «код»: «кг/m2»}},},.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-183">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="4f6d3-184">.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-184"></span></span>
        <span data-ttu-id="4f6d3-185">.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-185"></span></span>
      <span data-ttu-id="4f6d3-186">] }</span><span class="sxs-lookup"><span data-stu-id="4f6d3-186"></span></span>

* * *

<span data-ttu-id="4f6d3-187">Просмотреть [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) другие сведения в этом поле значение.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-187">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="4f6d3-188">Условие</span><span class="sxs-lookup"><span data-stu-id="4f6d3-188">Condition</span></span>

<span data-ttu-id="4f6d3-189">Далее представлены минимальные обязательные поля, которые представляют собой подмножество [профилей Argonaut условие](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="4f6d3-189">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="4f6d3-190">Code.Coding[0]. Отображение</span><span class="sxs-lookup"><span data-stu-id="4f6d3-190">Code.Coding[0].Display</span></span>

<span data-ttu-id="4f6d3-191">Помимо полей Argonaut удобную работу пользователя приложения пострадавших также содержатся следующие поля:</span><span class="sxs-lookup"><span data-stu-id="4f6d3-191">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="4f6d3-192">Дата записи</span><span class="sxs-lookup"><span data-stu-id="4f6d3-192">Date Recorded</span></span>
2. <span data-ttu-id="4f6d3-193">Уровень серьезности</span><span class="sxs-lookup"><span data-stu-id="4f6d3-193">Severity</span></span>

<span data-ttu-id="4f6d3-194">Поиск ресурсов используется метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="4f6d3-194">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4f6d3-195">пострадавший =\<пациента id></span><span class="sxs-lookup"><span data-stu-id="4f6d3-195">patient=\<patient id></span></span>
2. <span data-ttu-id="4f6d3-196">_count =\<максимальной results></span><span class="sxs-lookup"><span data-stu-id="4f6d3-196">_count=\<max results></span></span>

<span data-ttu-id="4f6d3-197">Можно найти в следующем примере этот вызов:</span><span class="sxs-lookup"><span data-stu-id="4f6d3-197">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="4f6d3-198">Запрос: Получение <fhir-server>/условие? пострадавший = <patient id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="4f6d3-198">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="4f6d3-199">Ответ: {«типа ресурса»: «Объединяют», «id»: «<bundle id>», «тип»: «searchset», «общее»: 1, «запись»: [{«ресурс»: {«типа ресурса»: «Условие», «id»: «<resource id>», «код»: {«создание кода»: [{               «система»: "http://snomed.info/sct«, «код»: «386033004», «отображение»: «Neuropathy (решений повреждение)»}]}, «dateRecorded»: «2018-09-17», «уровень серьезности»: {«создание кода»: [{«системы длинное»: "http://snomed.info/sct«, «код»: «24484000», «отображение»: «Серьезный»}]}},}]}</span><span class="sxs-lookup"><span data-stu-id="4f6d3-199">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="4f6d3-200">Просмотреть [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) другие сведения в этом поле значение.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-200">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="4f6d3-201">Встретиться</span><span class="sxs-lookup"><span data-stu-id="4f6d3-201">Encounter</span></span>

<span data-ttu-id="4f6d3-202">Далее представлены минимальные обязательные поля, которые представляют собой подмножество полей "мне Нравится" встретиться основных «должен иметь» профиль:</span><span class="sxs-lookup"><span data-stu-id="4f6d3-202">These are the minimum required fields, which are a subset of the US Core Encounter profile “must have” fields:</span></span>

1. <span data-ttu-id="4f6d3-203">Состояние</span><span class="sxs-lookup"><span data-stu-id="4f6d3-203">Status</span></span>
2. <span data-ttu-id="4f6d3-204">Тип [0]. Создание кода [0]. Отображение</span><span class="sxs-lookup"><span data-stu-id="4f6d3-204">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="4f6d3-205">Кроме того следующие поля из профиля "мне Нравится" встретиться Core «должна поддерживать» поля</span><span class="sxs-lookup"><span data-stu-id="4f6d3-205">In addition, the following fields from US Core Encounter profile’s “must support” fields</span></span>

1. <span data-ttu-id="4f6d3-206">Period.Start</span><span class="sxs-lookup"><span data-stu-id="4f6d3-206">Period.Start</span></span>
2. <span data-ttu-id="4f6d3-207">Расположение [0]. Location.Display</span><span class="sxs-lookup"><span data-stu-id="4f6d3-207">Location[0].Location.Display</span></span>

<span data-ttu-id="4f6d3-208">Поиск ресурсов используется метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="4f6d3-208">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4f6d3-209">пострадавший =\<пациента id></span><span class="sxs-lookup"><span data-stu-id="4f6d3-209">patient=\<patient id></span></span>
2. <span data-ttu-id="4f6d3-210">_sort:DESC =\<поля ex.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-210">_sort:desc=\<field ex.</span></span> <span data-ttu-id="4f6d3-211">date></span><span class="sxs-lookup"><span data-stu-id="4f6d3-211">date></span></span>
3. <span data-ttu-id="4f6d3-212">_count =\<максимальной results></span><span class="sxs-lookup"><span data-stu-id="4f6d3-212">_count=\<max results></span></span>

<span data-ttu-id="4f6d3-213">Цель — должны иметь возможность получения последнего заданного расположения пациента.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-213">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="4f6d3-214">Каждый обнаружения ссылается на расположение ресурса.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-214">Each encounter references a location resource.</span></span> <span data-ttu-id="4f6d3-215">Справочные материалы по должен также включать отображаемое поле расположение.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-215">The reference shall also include the location’s display field.</span></span> <span data-ttu-id="4f6d3-216">Следующий пример вызова см.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-216">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="4f6d3-217">Запрос: Получение <fhir-server>/обнаружения? пострадавший = <patient-id>&_sort:desc = date&_count = 1</span><span class="sxs-lookup"><span data-stu-id="4f6d3-217">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="4f6d3-218">Ответ: {«типа ресурса»: «Узел», «тип»: «searchset», «общее»: 1, «запись»: [{«ресурс»: {«типа ресурса»: «Встретиться», «id»: «<resource id>», «идентификатор»: [{«используйте»: «официальный», «значение»: "<id>"}], «состояние» : «было доставлено», «тип»: [{«создание кода»: [{«отображение»: «Встреча»}],}], «пациента»: {«ссылка»: «Пострадавший/<patient-id>»}, «период»: {«запуск»: «09/17/2018 1:00:00 PM»}, «расположение»: [{              «расположение»: {«отображение»: «ENT – семинар»},}]}}]}</span><span class="sxs-lookup"><span data-stu-id="4f6d3-218">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="4f6d3-219">Просмотреть [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) другие сведения в этом поле значение.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-219">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="4f6d3-220">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="4f6d3-220">AllergyIntolerance</span></span>

<span data-ttu-id="4f6d3-221">Далее представлены минимальные обязательные поля, которые представляют собой подмножество профилей Argonaut AllergyIntolerance:</span><span class="sxs-lookup"><span data-stu-id="4f6d3-221">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="4f6d3-222">Code.Text</span><span class="sxs-lookup"><span data-stu-id="4f6d3-222">Code.Text</span></span>
2. <span data-ttu-id="4f6d3-223">Code.Coding[0]. Отображение</span><span class="sxs-lookup"><span data-stu-id="4f6d3-223">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="4f6d3-224">Состояние</span><span class="sxs-lookup"><span data-stu-id="4f6d3-224">Status</span></span>

<span data-ttu-id="4f6d3-225">Помимо полей Argonaut для удобную работу пользователя приложения пострадавших также считывает следующие поля:</span><span class="sxs-lookup"><span data-stu-id="4f6d3-225">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="4f6d3-226">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="4f6d3-226">RecordedDate</span></span>
2. <span data-ttu-id="4f6d3-227">Note.Text</span><span class="sxs-lookup"><span data-stu-id="4f6d3-227">Note.Text</span></span>
3. <span data-ttu-id="4f6d3-228">Реакция [.]. Substance.Text</span><span class="sxs-lookup"><span data-stu-id="4f6d3-228">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="4f6d3-229">Реакция [.]. Проявление [.]. Текст</span><span class="sxs-lookup"><span data-stu-id="4f6d3-229">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="4f6d3-230">Text.Div</span><span class="sxs-lookup"><span data-stu-id="4f6d3-230">Text.Div</span></span>

<span data-ttu-id="4f6d3-231">Поиск ресурсов используется метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="4f6d3-231">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4f6d3-232">Пострадавший = \<пациента id></span><span class="sxs-lookup"><span data-stu-id="4f6d3-232">Patient =  \<patient id></span></span>

<span data-ttu-id="4f6d3-233">Можно найти в следующем примере этот вызов:</span><span class="sxs-lookup"><span data-stu-id="4f6d3-233">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="4f6d3-234">Запрос: Получение <fhir-server>/AllergyIntolerance? пострадавший = <patient id></span><span class="sxs-lookup"><span data-stu-id="4f6d3-234">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="4f6d3-235">Ответ: {«типа ресурса»: «Объединяют», «id»: «<bundle id>», «тип»: «searchset», «общее»: 1, «запись»: [{«ресурс»: {«типа ресурса»: «AllergyIntolerance», «id»: «<resource id>», «recordedDate»: «2018-09-17T07:00:00.00 0Z», «вещества»: {«текст»: «Cashew гайки»}, «состояние»: «подтверждено», «реакция»: [{«вещества»: {«текст»: «cashew гайки allergenic Извлеките Injectable продукта»}, manifestati « на»: [{«текст»: «Anaphylactic реакции»}]}]}}]}</span><span class="sxs-lookup"><span data-stu-id="4f6d3-235">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="4f6d3-236">Просмотреть [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) другие сведения в этом поле значение.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-236">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="4f6d3-237">Порядок лечения</span><span class="sxs-lookup"><span data-stu-id="4f6d3-237">Medication Order</span></span>

<span data-ttu-id="4f6d3-238">Далее представлены минимальные обязательные поля, которые представляют собой подмножество профилей Argonaut MedicationOrder:</span><span class="sxs-lookup"><span data-stu-id="4f6d3-238">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="4f6d3-239">DateWritten</span><span class="sxs-lookup"><span data-stu-id="4f6d3-239">DateWritten</span></span>
2. <span data-ttu-id="4f6d3-240">Prescriber.Display</span><span class="sxs-lookup"><span data-stu-id="4f6d3-240">Prescriber.Display</span></span>
3. <span data-ttu-id="4f6d3-241">Medication.Display (если ссылки)</span><span class="sxs-lookup"><span data-stu-id="4f6d3-241">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="4f6d3-242">Medication.Text (если концепция)</span><span class="sxs-lookup"><span data-stu-id="4f6d3-242">Medication.Text (if concept)</span></span>

<span data-ttu-id="4f6d3-243">Помимо полей Argonaut удобную работу пользователя приложения пострадавших также содержатся следующие поля:</span><span class="sxs-lookup"><span data-stu-id="4f6d3-243">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="4f6d3-244">DateEnded</span><span class="sxs-lookup"><span data-stu-id="4f6d3-244">DateEnded</span></span>
2. <span data-ttu-id="4f6d3-245">DosageInstruction.Text</span><span class="sxs-lookup"><span data-stu-id="4f6d3-245">DosageInstruction.Text</span></span>
3. <span data-ttu-id="4f6d3-246">Text.Div</span><span class="sxs-lookup"><span data-stu-id="4f6d3-246">Text.Div</span></span>

<span data-ttu-id="4f6d3-247">Поиск ресурсов используется метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="4f6d3-247">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4f6d3-248">пострадавший =\<пациента id></span><span class="sxs-lookup"><span data-stu-id="4f6d3-248">patient=\<patient id></span></span>
2. <span data-ttu-id="4f6d3-249">_count =\<максимальной results></span><span class="sxs-lookup"><span data-stu-id="4f6d3-249">_count=\<max results></span></span>

<span data-ttu-id="4f6d3-250">Можно найти в следующем примере этот вызов:</span><span class="sxs-lookup"><span data-stu-id="4f6d3-250">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="4f6d3-251">Запрос: Получение <fhir-server>/MedicationOrder? пострадавший = <patient id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="4f6d3-251">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="4f6d3-252">Ответ: {«типа ресурса»: «Объединяют», «id»: «<bundle id>», «тип»: «searchset», «общее»: 1, «запись»: [{«ресурс»: {«типа ресурса»: «MedicationOrder», «id»: «<resource id>», «dateWritten»: «2018-09-17", «мультимедиа cationCodeableConcept»: {«текст»: «Lisinopril 20 МБ устные планшетного ПК»}, «prescriber»: {«отображение»: «Иван Петров»}, «dosageInstruction»: [{«текст»: «1 ежедневно»}]}}]}</span><span class="sxs-lookup"><span data-stu-id="4f6d3-252">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="4f6d3-253">Просмотреть [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) другие сведения в этом поле значение.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-253">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="4f6d3-254">Покрытия</span><span class="sxs-lookup"><span data-stu-id="4f6d3-254">Coverage</span></span>

<span data-ttu-id="4f6d3-255">Далее представлены минимальные обязательные поля, не принадлежат основные "мне Нравится" или Argonaut профилей:</span><span class="sxs-lookup"><span data-stu-id="4f6d3-255">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="4f6d3-256">Payor</span><span class="sxs-lookup"><span data-stu-id="4f6d3-256">Payor</span></span>

<span data-ttu-id="4f6d3-257">Поиск ресурсов используется метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="4f6d3-257">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4f6d3-258">пострадавший =\<пациента id></span><span class="sxs-lookup"><span data-stu-id="4f6d3-258">patient=\<patient id></span></span>

<span data-ttu-id="4f6d3-259">Можно найти в следующем примере этот вызов:</span><span class="sxs-lookup"><span data-stu-id="4f6d3-259">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="4f6d3-260">Запрос: Получение <fhir-server>/покрытия? пострадавший = <patient id></span><span class="sxs-lookup"><span data-stu-id="4f6d3-260">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="4f6d3-261">Ответ: {«типа ресурса»: «Узел», «тип»: «searchset», «общее»: 1, «запись»: [{«ресурс»: {«типа ресурса»: «Обслуживание», «id»: «<resource id>», «план»: «No основной страхования», «подписчик»: {«ссылка»: «пострадавший / <patient id>»}}}]}</span><span class="sxs-lookup"><span data-stu-id="4f6d3-261">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="4f6d3-262">Просмотреть [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) другие сведения в этом поле значение.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-262">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="4f6d3-263">Местоположение</span><span class="sxs-lookup"><span data-stu-id="4f6d3-263">Location</span></span>

<span data-ttu-id="4f6d3-264">Этот ресурс используется как ссылка на ресурс [возникать](#encounter) .</span><span class="sxs-lookup"><span data-stu-id="4f6d3-264">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="4f6d3-265">Просмотреть [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) другие сведения в этом поле значение.</span><span class="sxs-lookup"><span data-stu-id="4f6d3-265">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
