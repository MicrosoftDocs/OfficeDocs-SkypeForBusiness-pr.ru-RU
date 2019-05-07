---
title: Приложение пациентов и EHR интеграции STU3 интерфейс
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
ms.openlocfilehash: 34fd6bb1ecaf788a55aca877c671c9a51cb07944
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643128"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="fa8ea-103">Спецификации интерфейса STU3</span><span class="sxs-lookup"><span data-stu-id="fa8ea-103">STU3 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="fa8ea-104">Настройка или перенастройка сервер FHIR для работы с приложением Microsoft группами пострадавших необходимо понимание того, какие данные требуется доступ к приложению.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="fa8ea-105">FHIR сервер должен поддерживать запросы POST, с помощью пакета для со следующими ресурсами:</span><span class="sxs-lookup"><span data-stu-id="fa8ea-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="fa8ea-106">Пострадавший</span><span class="sxs-lookup"><span data-stu-id="fa8ea-106">Patient</span></span>](#patient)
- [<span data-ttu-id="fa8ea-107">Наблюдения</span><span class="sxs-lookup"><span data-stu-id="fa8ea-107">Observation</span></span>](#observation)
- [<span data-ttu-id="fa8ea-108">Условие</span><span class="sxs-lookup"><span data-stu-id="fa8ea-108">Condition</span></span>](#condition)
- [<span data-ttu-id="fa8ea-109">Встретиться</span><span class="sxs-lookup"><span data-stu-id="fa8ea-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="fa8ea-110">Intolerance аллергических реакций</span><span class="sxs-lookup"><span data-stu-id="fa8ea-110">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="fa8ea-111">Покрытия</span><span class="sxs-lookup"><span data-stu-id="fa8ea-111">Coverage</span></span>](#coverage)
- <span data-ttu-id="fa8ea-112">[Оператор лечения](#medication-request) (заменяет MedicationOrder в версии DSTU2 PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="fa8ea-112">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="fa8ea-113">Расположение (сведения о необходимости из этот ресурс может быть включен в обнаружения)</span><span class="sxs-lookup"><span data-stu-id="fa8ea-113">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="fa8ea-114">Пациента ресурсов — это единственная обязательная ресурсов, (без которой приложение не будут загружаться на всех); Тем не менее рекомендуется, что партнера реализации поддержки выше ресурсов на спецификации представлены ниже для рекомендации для конечных пользователей с группами пострадавших Microsoft App.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-114">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="fa8ea-115">Запросы из приложения пострадавших группами Майкрософт для нескольких ресурсов должна учитывать пакета (пакет) запросов на URL-адрес сервера FHIR.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-115">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="fa8ea-116">Сервер должен обработать каждого запроса и вернуть набор ресурсов, совпадающих с каждого запроса.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-116">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="fa8ea-117">Дополнительные сведения и примеры, в разделе [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span><span class="sxs-lookup"><span data-stu-id="fa8ea-117">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="fa8ea-118">Возможность оператор</span><span class="sxs-lookup"><span data-stu-id="fa8ea-118">Capability Statement</span></span>

<span data-ttu-id="fa8ea-119">Далее представлены минимальные обязательные поля:</span><span class="sxs-lookup"><span data-stu-id="fa8ea-119">These are the minimum required fields:</span></span>

1. <span data-ttu-id="fa8ea-120">REST</span><span class="sxs-lookup"><span data-stu-id="fa8ea-120">REST</span></span>
   1. <span data-ttu-id="fa8ea-121">Режим</span><span class="sxs-lookup"><span data-stu-id="fa8ea-121">Mode</span></span>
   2. <span data-ttu-id="fa8ea-122">Взаимодействие</span><span class="sxs-lookup"><span data-stu-id="fa8ea-122">Interaction</span></span>
   3. <span data-ttu-id="fa8ea-123">Ресурс: тип</span><span class="sxs-lookup"><span data-stu-id="fa8ea-123">Resource: Type</span></span>
   4. <span data-ttu-id="fa8ea-124">Безопасность: [расширения для URI OAuth](http://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="fa8ea-124">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="fa8ea-125">FhirVersion (код требует, чтобы она понять, какие версии, мы должны вводить несколько.)</span><span class="sxs-lookup"><span data-stu-id="fa8ea-125">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="fa8ea-126">Просмотреть [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) другие сведения в этом поле значение.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-126">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="fa8ea-127">Пострадавший</span><span class="sxs-lookup"><span data-stu-id="fa8ea-127">Patient</span></span>

<span data-ttu-id="fa8ea-128">Ниже приведены минимальные обязательные поля, которые представляют собой подмножество полей Argonaut пациента профилей.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-128">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="fa8ea-129">Name.Given</span><span class="sxs-lookup"><span data-stu-id="fa8ea-129">Name.Given</span></span>
2. <span data-ttu-id="fa8ea-130">Name.Family</span><span class="sxs-lookup"><span data-stu-id="fa8ea-130">Name.Family</span></span>
3. <span data-ttu-id="fa8ea-131">Пол</span><span class="sxs-lookup"><span data-stu-id="fa8ea-131">Gender</span></span>
4. <span data-ttu-id="fa8ea-132">Дата рождения</span><span class="sxs-lookup"><span data-stu-id="fa8ea-132">BirthDate</span></span>
5. <span data-ttu-id="fa8ea-133">MRN (идентификатор)</span><span class="sxs-lookup"><span data-stu-id="fa8ea-133">MRN (Identifier)</span></span>

<span data-ttu-id="fa8ea-134">Помимо [полей Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)удобную работу пользователя приложения пострадавших также содержатся следующие поля:</span><span class="sxs-lookup"><span data-stu-id="fa8ea-134">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="fa8ea-135">Name.Use</span><span class="sxs-lookup"><span data-stu-id="fa8ea-135">Name.Use</span></span>
2. <span data-ttu-id="fa8ea-136">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="fa8ea-136">Name.Prefix</span></span>
3. <span data-ttu-id="fa8ea-137">[GeneralPractitioner] - GeneralPractitioner ссылку должно быть включено в пациента ресурсов (только отображаемое поле)</span><span class="sxs-lookup"><span data-stu-id="fa8ea-137">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="fa8ea-138">Поиск ресурсов использует метод POST на /Patient/_search and следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fa8ea-138">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="fa8ea-139">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="fa8ea-139">id</span></span>
2. <span data-ttu-id="fa8ea-140">Семейство = (поиск всех пострадавших семейства, имя которого содержит значение)</span><span class="sxs-lookup"><span data-stu-id="fa8ea-140">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="fa8ea-141">Данный =\<substring></span><span class="sxs-lookup"><span data-stu-id="fa8ea-141">given=\<substring></span></span>
4. <span data-ttu-id="fa8ea-142">Дата рождения =(exact match)</span><span class="sxs-lookup"><span data-stu-id="fa8ea-142">birthdate=(exact match)</span></span>
5. <span data-ttu-id="fa8ea-143">Пол = (значения из административных Пол)</span><span class="sxs-lookup"><span data-stu-id="fa8ea-143">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="fa8ea-144">\_Count (максимальное количество результатов, которые должны быть возвращены)</span><span class="sxs-lookup"><span data-stu-id="fa8ea-144">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="fa8ea-145">Ответ должен содержать общее число записей, возвращаемых в результате поиска и \_count будут использовать PatientsApp для ограничения числа возвращаемых записей.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-145">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="fa8ea-146">Идентификатор =\<mrn></span><span class="sxs-lookup"><span data-stu-id="fa8ea-146">identifier=\<mrn></span></span>

<span data-ttu-id="fa8ea-147">Цель — должны иметь возможность поиска и фильтров для пострадавший следующими службами:</span><span class="sxs-lookup"><span data-stu-id="fa8ea-147">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="fa8ea-148">ID — Это идентификатор ресурсов, у каждого ресурса FHIR.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-148">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="fa8ea-149">MRN: Это фактический идентификатор пациент, знать клинических персонала.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-149">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="fa8ea-150">Мы понимаем, это MRN, основанные на тип идентификатора внутри идентификатор ресурса в FHIR.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-150">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="fa8ea-151">Имя</span><span class="sxs-lookup"><span data-stu-id="fa8ea-151">Name</span></span>
- <span data-ttu-id="fa8ea-152">Дата рождения</span><span class="sxs-lookup"><span data-stu-id="fa8ea-152">Birthdate</span></span>

<span data-ttu-id="fa8ea-153">Рассмотрим следующий пример вызова:</span><span class="sxs-lookup"><span data-stu-id="fa8ea-153">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="fa8ea-154">Запрос: <fhir-server>/пострадавший/_search запросить запроса POST: заданного = ruth&family = черный</span><span class="sxs-lookup"><span data-stu-id="fa8ea-154">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="fa8ea-155">Ответ: {«типа ресурса»: «Объединяют», «id»: «<bundle id>», «meta»: {«lastUpdated»: «2019-01-14T23:44:45.052 + 00:00 "}, «тип»: «searchset», «общее»: 1, «ссылка»: [{«связь»: «self», «URL-адрес»: <fhir-server>/пострадавший/_search»}], «запись»: [{ «параметре fullUrl»: <fhir-server>/пострадавший/<patient-id>», «ресурс»: {«типа ресурса»: «Пациента», «id»: «<patient id>», «meta»: {«versionId»: «1», «lastUpdated»: «2017-10-18T18:32:37.000 + 00:00 "}, «текст»: {«статус»: «создан», «div ": "</span><span class="sxs-lookup"><span data-stu-id="fa8ea-155">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="fa8ea-156">\n</span><span class="sxs-lookup"><span data-stu-id="fa8ea-156">\n</span></span>        <p><span data-ttu-id="fa8ea-157">Черный Ruth</span><span class="sxs-lookup"><span data-stu-id="fa8ea-157">Ruth Black</span></span></p><span data-ttu-id="fa8ea-158">\n</span><span class="sxs-lookup"><span data-stu-id="fa8ea-158">\n</span></span>      </div><span data-ttu-id="fa8ea-159">"}, «идентификатор»: [{«используйте»: «обычный», «тип»: {«создание кода»: [{«система»:"http://hl7.org/fhir/v2/0203«, «код»: «MR», «отображение»: «номер медицинского обслуживания записи», «userSelected»: false}], «текст»: «номер медицинского обслуживания записи»}, «система»: "http://hospital.smarthealthit.org«, «значение»: «1234567»}], «активно»: имеет значение true," Имя»: [{«используйте»: «официальный», «семья»: «Черный», «присвоенное»: [«Ruth», «c».</span><span class="sxs-lookup"><span data-stu-id="fa8ea-159">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="fa8ea-160">[]}], «связи»: [{«система»: «телефон», «значение»: «800-599-2739", «использование»: «домашний»}, {«система»: «телефон», «значение»: «800-808-7785", «использование»: «мобильных»}, {«система»: «электронная почта», «значение»: «ruth.black@example.com»}], «Пол»: «гнездо», «Дата рождения»: «1951-08-23"," адрес»: [{«используйте»: «Домашняя страница», «строка»: [«26 Южная RdApt 22»], «Город»: «Sapulpa», «состояние»: «ОК», «индекс»: «74066», «Страна»: «США»}]}, «поиск»: {«режима»: «match»}}]}</span><span class="sxs-lookup"><span data-stu-id="fa8ea-160">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="fa8ea-161">Запрос: Получение <fhir-server>/пострадавший/<patient-id></span><span class="sxs-lookup"><span data-stu-id="fa8ea-161">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="fa8ea-162">Ответ: {«типа ресурса»: «Пациента», «id»: «<patient id>», «идентификатор»: [{«используйте»: «обычный», «тип»: {«создание кода»: [{«система»: "http://hl7.org/fhir/v2/0203«, «код»: «MR»}], «текст»: «номер медицинского обслуживания записи»}, «значение»: «1234567»}], «имя»: [{«используйте»: «официальный», « Семейство»: «Adams», «учитывая»: [«Дэниэла», «X».</span><span class="sxs-lookup"><span data-stu-id="fa8ea-162">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="fa8ea-163">] {}], «Пол»: «штекер», «Дата рождения»: «с использованием 1925-12-23"}</span><span class="sxs-lookup"><span data-stu-id="fa8ea-163">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="fa8ea-164">Просмотреть [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) другие сведения в этом поле значение.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-164">See [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="fa8ea-165">Наблюдения</span><span class="sxs-lookup"><span data-stu-id="fa8ea-165">Observation</span></span>

<span data-ttu-id="fa8ea-166">Далее представлены минимальные обязательные поля, которые представляют собой подмножество [основных Argonaut-показателей профилей](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span><span class="sxs-lookup"><span data-stu-id="fa8ea-166">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="fa8ea-167">Эффективного (дата, время или периода)</span><span class="sxs-lookup"><span data-stu-id="fa8ea-167">Effective (date time or period)</span></span>
2. <span data-ttu-id="fa8ea-168">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="fa8ea-168">Code.Coding.Code</span></span>
3. <span data-ttu-id="fa8ea-169">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="fa8ea-169">ValueQuantity.Value</span></span>

<span data-ttu-id="fa8ea-170">Помимо полей Argonaut удобную работу пользователя приложения пострадавших также содержатся следующие поля:</span><span class="sxs-lookup"><span data-stu-id="fa8ea-170">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="fa8ea-171">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="fa8ea-171">Code.Coding.Display</span></span>
2. <span data-ttu-id="fa8ea-172">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="fa8ea-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="fa8ea-173">Поиск ресурсов используется метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fa8ea-173">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="fa8ea-174">пострадавший =\<пациента id></span><span class="sxs-lookup"><span data-stu-id="fa8ea-174">patient=\<patient id></span></span>
2. <span data-ttu-id="fa8ea-175">= _sort-даты</span><span class="sxs-lookup"><span data-stu-id="fa8ea-175">_sort=-date</span></span>
3. <span data-ttu-id="fa8ea-176">категории (мы будет запрашивать «категория = важной знаки») для получения списка основные показатели.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-176">category (we will query for “category=vital-signs”) to retrieve the list of vital signs.</span></span>

<span data-ttu-id="fa8ea-177">Обратитесь в этом примере вызов:</span><span class="sxs-lookup"><span data-stu-id="fa8ea-177">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="fa8ea-178">Запрос: Получение <fhir-server>/наблюдения? пострадавший = <patient id>&category = важной знаки</span><span class="sxs-lookup"><span data-stu-id="fa8ea-178">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="fa8ea-179">Ответ: {«типа ресурса»: «Объединяют», «id»: «<bundle id>», «тип»: «searchset», «общее»: 20, «запись»: [{«ресурс»: {«типа ресурса»: «Наблюдение», «id»: «<resource id>», «Категория»: [{«создание кода»: [{«система»: "http://hl7.org/fhir/observation-category«, «код»: « важной знаки»}],}], «кода»: {«создание кода»: [{«система»: "http://loinc.org«, «код»: «8867-4», «отображение»: «heart_rate»}]}, «effectiveDateTime»: «2009 г.-04-08T00:00:00-06:00», «valueQuantity»: {«значение»: 72.0, «единицы»: «{побивает} / мин.», «система»:"http://unitsofmeasure.org«,}}},.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-179">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "http://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="fa8ea-180">.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-180"></span></span>
        <span data-ttu-id="fa8ea-181">.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-181"></span></span>
      <span data-ttu-id="fa8ea-182">] }</span><span class="sxs-lookup"><span data-stu-id="fa8ea-182"></span></span>

* * *

<span data-ttu-id="fa8ea-183">Просмотреть [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) другие сведения в этом поле значение.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-183">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="fa8ea-184">Условие</span><span class="sxs-lookup"><span data-stu-id="fa8ea-184">Condition</span></span>

<span data-ttu-id="fa8ea-185">Вот минимальные обязательные поля, которые представляют собой подмножество [Argonaut условие профилей](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span><span class="sxs-lookup"><span data-stu-id="fa8ea-185">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="fa8ea-186">Code.Coding[0]. Отображение</span><span class="sxs-lookup"><span data-stu-id="fa8ea-186">Code.Coding[0].Display</span></span>

<span data-ttu-id="fa8ea-187">Помимо полей Argonaut удобную работу пользователя приложения пострадавших также содержатся следующие поля:</span><span class="sxs-lookup"><span data-stu-id="fa8ea-187">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="fa8ea-188">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="fa8ea-188">AssertedDate</span></span>
2. <span data-ttu-id="fa8ea-189">Уровень серьезности</span><span class="sxs-lookup"><span data-stu-id="fa8ea-189">Severity</span></span>

<span data-ttu-id="fa8ea-190">Поиск ресурсов используется метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fa8ea-190">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="fa8ea-191">пострадавший =\<пациента id></span><span class="sxs-lookup"><span data-stu-id="fa8ea-191">patient=\<patient id></span></span>
2. <span data-ttu-id="fa8ea-192">_count =\<максимальной results></span><span class="sxs-lookup"><span data-stu-id="fa8ea-192">_count=\<max results></span></span>

<span data-ttu-id="fa8ea-193">Можно найти в следующем примере этот вызов:</span><span class="sxs-lookup"><span data-stu-id="fa8ea-193">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="fa8ea-194">Запрос: Получение <fhir-server>/условие? пострадавший = <patient id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="fa8ea-194">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="fa8ea-195">Ответ: {«типа ресурса»: «Объединяют», «id»: «<bundle id>», «тип»: «searchset», «общее»: 2, «запись»: [{«ресурс»: {«типа ресурса»: «Условие», «id»: «<resource id>», «код»: {«создание кода»: [{«система»: "http://snomed.info/sct«, «код»: «185903001», « Отображение»: «Immunization influenza потребности,»}]}, «уровень серьезности»: {«создание кода»: [{«система»: "http://snomed.info/sct«, «код»: «24484000», «отображение»: «Серьезный»}]}, «assertedDate»: «2018-04-04»}},.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-195">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="fa8ea-196">.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-196"></span></span>
        <span data-ttu-id="fa8ea-197">.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-197"></span></span>
      <span data-ttu-id="fa8ea-198">] }</span><span class="sxs-lookup"><span data-stu-id="fa8ea-198"></span></span>

* * *
<span data-ttu-id="fa8ea-199">Просмотреть [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) другие сведения в этом поле значение.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-199">See [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="fa8ea-200">Встретиться</span><span class="sxs-lookup"><span data-stu-id="fa8ea-200">Encounter</span></span>

<span data-ttu-id="fa8ea-201">Далее представлены минимальные обязательные поля, которые представляют собой подмножество полей «должен иметь» [профиля возникать ядра в США](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) ).</span><span class="sxs-lookup"><span data-stu-id="fa8ea-201">These are the minimum required fields, which are a subset of the [US Core Encounter profile](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) “must have” fields).</span></span>

1. <span data-ttu-id="fa8ea-202">Состояние</span><span class="sxs-lookup"><span data-stu-id="fa8ea-202">Status</span></span>
2. <span data-ttu-id="fa8ea-203">Тип [0]. Создание кода [0]. Отображение</span><span class="sxs-lookup"><span data-stu-id="fa8ea-203">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="fa8ea-204">Кроме того следующие поля из профиля "мне Нравится" встретиться Core «должна поддерживать» поля:</span><span class="sxs-lookup"><span data-stu-id="fa8ea-204">In addition, the following fields from US Core Encounter profile’s “must support” fields:</span></span>

1. <span data-ttu-id="fa8ea-205">Period.Start</span><span class="sxs-lookup"><span data-stu-id="fa8ea-205">Period.Start</span></span>
2. <span data-ttu-id="fa8ea-206">Расположение [0]. Location.Display</span><span class="sxs-lookup"><span data-stu-id="fa8ea-206">Location[0].Location.Display</span></span>

<span data-ttu-id="fa8ea-207">Поиск ресурсов используется метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fa8ea-207">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="fa8ea-208">пострадавший =\<пациента id></span><span class="sxs-lookup"><span data-stu-id="fa8ea-208">patient=\<patient id></span></span>
2. <span data-ttu-id="fa8ea-209">_sort:DESC =\<поля ex.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-209">_sort:desc=\<field ex.</span></span> <span data-ttu-id="fa8ea-210">date></span><span class="sxs-lookup"><span data-stu-id="fa8ea-210">date></span></span>
3. <span data-ttu-id="fa8ea-211">_count =\<максимальной results></span><span class="sxs-lookup"><span data-stu-id="fa8ea-211">_count=\<max results></span></span>

<span data-ttu-id="fa8ea-212">Цель — должны иметь возможность получения последнего заданного расположения пациента.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-212">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="fa8ea-213">Каждый обнаружения ссылается на расположение ресурса.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-213">Each encounter references a location resource.</span></span> <span data-ttu-id="fa8ea-214">Справочные материалы по должен также включать отображаемое поле расположение.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-214">The reference shall also include the location’s display field.</span></span>

<span data-ttu-id="fa8ea-215">Просмотреть [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) другие сведения в этом поле значение.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-215">See [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="fa8ea-216">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="fa8ea-216">AllergyIntolerance</span></span>

<span data-ttu-id="fa8ea-217">Далее представлены минимальные обязательные поля, которые представляют собой подмножество профилей [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :</span><span class="sxs-lookup"><span data-stu-id="fa8ea-217">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="fa8ea-218">Code.Text</span><span class="sxs-lookup"><span data-stu-id="fa8ea-218">Code.Text</span></span>
2. <span data-ttu-id="fa8ea-219">Code.Coding[0]. Отображение</span><span class="sxs-lookup"><span data-stu-id="fa8ea-219">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="fa8ea-220">ClinicalStatus/VerificationStatus (мы читать оба)</span><span class="sxs-lookup"><span data-stu-id="fa8ea-220">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="fa8ea-221">Помимо полей Argonaut удобную работу пользователя приложения пострадавших также содержатся следующие поля:</span><span class="sxs-lookup"><span data-stu-id="fa8ea-221">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="fa8ea-222">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="fa8ea-222">AssertedDate</span></span>
2. <span data-ttu-id="fa8ea-223">Note.Text</span><span class="sxs-lookup"><span data-stu-id="fa8ea-223">Note.Text</span></span>
3. <span data-ttu-id="fa8ea-224">Реакция</span><span class="sxs-lookup"><span data-stu-id="fa8ea-224">Reaction</span></span>
    1. <span data-ttu-id="fa8ea-225">Вещества (один элемент написания кода)</span><span class="sxs-lookup"><span data-stu-id="fa8ea-225">Substance (one coding element)</span></span>
    2. <span data-ttu-id="fa8ea-226">Проявление (один элемент написания кода)</span><span class="sxs-lookup"><span data-stu-id="fa8ea-226">Manifestation (one coding element)</span></span>

<span data-ttu-id="fa8ea-227">Поиск ресурсов используется метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fa8ea-227">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="fa8ea-228">Пострадавший = \<пациента id></span><span class="sxs-lookup"><span data-stu-id="fa8ea-228">Patient =  \<patient id></span></span>

<span data-ttu-id="fa8ea-229">Рассмотрим следующий пример вызова:</span><span class="sxs-lookup"><span data-stu-id="fa8ea-229">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="fa8ea-230">Запрос: Получение <fhir-server>/AllergyIntolerance? пострадавший = <patient id></span><span class="sxs-lookup"><span data-stu-id="fa8ea-230">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="fa8ea-231">Ответ: {«типа ресурса»: «Объединяют», «id»: «<bundle id>», «тип»: «searchset», «общее»: 1, «запись»: [{«ресурс»: {«типа ресурса»: «AllergyIntolerance», «id»: «<resource id>», «clinicalStatus»: «активно», «сохранить rificationStatus»: «подтверждено», «код»: {«создание кода»: [{«система»: "http://rxnav.nlm.nih.gov/REST/Ndfrt«, «код»: «N0000175503», «отображение»: «sulfonamide antibacterial»,}], «текст»: «sulfonamide безопасности [[[ibacterial»}, «assertedDate»: «2018-01-01T00:00:00-07:00», «реакция»: [{«проявление»: [{«создание кода»: [{«система»: "http://snomed.info/sct«, «код»:  «271807003», «отображение»: «rash обложки,»}], «текст»: «обложки rash»}],}]}}]}</span><span class="sxs-lookup"><span data-stu-id="fa8ea-231">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="fa8ea-232">Просмотреть [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) другие сведения в этом поле значение.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-232">See [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="fa8ea-233">Запрос лечения</span><span class="sxs-lookup"><span data-stu-id="fa8ea-233">Medication Request</span></span>

<span data-ttu-id="fa8ea-234">Далее представлены минимальные обязательные поля, которые представляют собой подмножество [США основных лечения запросить профиль](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="fa8ea-234">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="fa8ea-235">Medication.Display (если ссылки)</span><span class="sxs-lookup"><span data-stu-id="fa8ea-235">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="fa8ea-236">Medication.Text (если CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="fa8ea-236">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="fa8ea-237">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="fa8ea-237">AuthoredOn</span></span>
4. <span data-ttu-id="fa8ea-238">Requester.Agent.Display</span><span class="sxs-lookup"><span data-stu-id="fa8ea-238">Requester.Agent.Display</span></span>

<span data-ttu-id="fa8ea-239">В дополнение к нам основных полей удобную работу пользователя приложения пострадавших также содержатся следующие поля:</span><span class="sxs-lookup"><span data-stu-id="fa8ea-239">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="fa8ea-240">DosageInstruction [.]. Текст</span><span class="sxs-lookup"><span data-stu-id="fa8ea-240">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="fa8ea-241">Текст</span><span class="sxs-lookup"><span data-stu-id="fa8ea-241">Text</span></span>

<span data-ttu-id="fa8ea-242">Поиск ресурсов используется метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fa8ea-242">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="fa8ea-243">пострадавший =\<пациента id></span><span class="sxs-lookup"><span data-stu-id="fa8ea-243">patient=\<patient id></span></span>
2. <span data-ttu-id="fa8ea-244">_count =\<максимальной results></span><span class="sxs-lookup"><span data-stu-id="fa8ea-244">_count=\<max results></span></span>

<span data-ttu-id="fa8ea-245">Просмотреть [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) другие сведения в этом поле значение.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-245">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="fa8ea-246">Покрытия</span><span class="sxs-lookup"><span data-stu-id="fa8ea-246">Coverage</span></span>

<span data-ttu-id="fa8ea-247">Далее представлены минимальные обязательные поля, не принадлежат основные "мне Нравится" или Argonaut профилей:</span><span class="sxs-lookup"><span data-stu-id="fa8ea-247">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="fa8ea-248">Группировка, по крайней мере один элемент с</span><span class="sxs-lookup"><span data-stu-id="fa8ea-248">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="fa8ea-249">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="fa8ea-249">GroupDisplay</span></span>
    2. <span data-ttu-id="fa8ea-250">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="fa8ea-250">PlanDisplay</span></span>
2. <span data-ttu-id="fa8ea-251">Период</span><span class="sxs-lookup"><span data-stu-id="fa8ea-251">Period</span></span>
3. <span data-ttu-id="fa8ea-252">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="fa8ea-252">SubscriberId</span></span>

<span data-ttu-id="fa8ea-253">Поиск ресурсов используется метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fa8ea-253">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="fa8ea-254">Пострадавший = \<пациента id></span><span class="sxs-lookup"><span data-stu-id="fa8ea-254">Patient = \<patient id></span></span>

<span data-ttu-id="fa8ea-255">Просмотреть [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) другие сведения в этом поле значение.</span><span class="sxs-lookup"><span data-stu-id="fa8ea-255">See [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
