---
title: Интерфейс STU3 пациентов для приложений и ехр интеграции
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Интеграция приложений Microsoft Teams пациентов ехр
ms.openlocfilehash: 836c28f339a3936f03315b005c0eedfc49e0f2ba
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569247"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="f18da-103">Характеристики интерфейса STU3</span><span class="sxs-lookup"><span data-stu-id="f18da-103">STU3 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="f18da-104">Настройка или перенастройка сервера ФХИР для работы с приложением Microsoft Teams пациентов требует понимания данных, к которым приложению требуется доступ.</span><span class="sxs-lookup"><span data-stu-id="f18da-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="f18da-105">Сервер ФХИР должен поддерживать запросы POST, используя пакеты для указанных ниже ресурсов.</span><span class="sxs-lookup"><span data-stu-id="f18da-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="f18da-106">Подождите</span><span class="sxs-lookup"><span data-stu-id="f18da-106">Patient</span></span>](#patient)
- [<span data-ttu-id="f18da-107">Наблюдение</span><span class="sxs-lookup"><span data-stu-id="f18da-107">Observation</span></span>](#observation)
- [<span data-ttu-id="f18da-108">Условие</span><span class="sxs-lookup"><span data-stu-id="f18da-108">Condition</span></span>](#condition)
- [<span data-ttu-id="f18da-109">Происходит</span><span class="sxs-lookup"><span data-stu-id="f18da-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="f18da-110">Недопустимый аллерги</span><span class="sxs-lookup"><span data-stu-id="f18da-110">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="f18da-111">Приложения</span><span class="sxs-lookup"><span data-stu-id="f18da-111">Coverage</span></span>](#coverage)
- <span data-ttu-id="f18da-112">[Оператор лечения](#medication-request) (заменяет МЕДИКАТИОНОРДЕР в DSTU2 версии патиентсапп)</span><span class="sxs-lookup"><span data-stu-id="f18da-112">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="f18da-113">Расположение (данные, необходимые для этого ресурса, могут быть включены в план)</span><span class="sxs-lookup"><span data-stu-id="f18da-113">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="f18da-114">Ресурс пациент является единственным обязательным ресурсом (без которого приложение не будет загружаться вообще); Тем не менее, рекомендуется, чтобы партнеры реализовали поддержку всех вышеупомянутых ресурсов для спецификаций, указанных ниже, для наилучшего взаимодействия с пользователем в приложении Microsoft Teams пациентов.</span><span class="sxs-lookup"><span data-stu-id="f18da-114">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="f18da-115">Запросы из приложения Microsoft Teams пациентов для более чем одного ресурса должны публиковать набор (пакет) запросов на URL-адрес сервера ФХИР.</span><span class="sxs-lookup"><span data-stu-id="f18da-115">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="f18da-116">Сервер должен обрабатывать каждый запрос и возвращать набор ресурсов, соответствующих каждому запросу.</span><span class="sxs-lookup"><span data-stu-id="f18da-116">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="f18da-117">Дополнительные сведения и примеры можно найти в [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction)разделе.</span><span class="sxs-lookup"><span data-stu-id="f18da-117">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="f18da-118">Оператор возможностей</span><span class="sxs-lookup"><span data-stu-id="f18da-118">Capability Statement</span></span>

<span data-ttu-id="f18da-119">Ниже указаны минимальные обязательные поля.</span><span class="sxs-lookup"><span data-stu-id="f18da-119">These are the minimum required fields:</span></span>

1. <span data-ttu-id="f18da-120">ДЕРЖИВАЕТ</span><span class="sxs-lookup"><span data-stu-id="f18da-120">REST</span></span>
   1. <span data-ttu-id="f18da-121">Режиме</span><span class="sxs-lookup"><span data-stu-id="f18da-121">Mode</span></span>
   2. <span data-ttu-id="f18da-122">Действует</span><span class="sxs-lookup"><span data-stu-id="f18da-122">Interaction</span></span>
   3. <span data-ttu-id="f18da-123">Ресурс: тип</span><span class="sxs-lookup"><span data-stu-id="f18da-123">Resource: Type</span></span>
   4. <span data-ttu-id="f18da-124">Безопасность: [расширение URI OAuth](http://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="f18da-124">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="f18da-125">Фхирверсион (для нашего кода требуется, чтобы узнать, в какую версию следует поворачивать.)</span><span class="sxs-lookup"><span data-stu-id="f18da-125">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="f18da-126">Дополнительные [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="f18da-126">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="f18da-127">Подождите</span><span class="sxs-lookup"><span data-stu-id="f18da-127">Patient</span></span>

<span data-ttu-id="f18da-128">Ниже приведены минимальные обязательные поля, которые являются подмножеством полей профиля пациента Аргонаут:</span><span class="sxs-lookup"><span data-stu-id="f18da-128">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="f18da-129">Name (имя). задано</span><span class="sxs-lookup"><span data-stu-id="f18da-129">Name.Given</span></span>
2. <span data-ttu-id="f18da-130">Family (имя)</span><span class="sxs-lookup"><span data-stu-id="f18da-130">Name.Family</span></span>
3. <span data-ttu-id="f18da-131">Полу</span><span class="sxs-lookup"><span data-stu-id="f18da-131">Gender</span></span>
4. <span data-ttu-id="f18da-132">Рождения</span><span class="sxs-lookup"><span data-stu-id="f18da-132">BirthDate</span></span>
5. <span data-ttu-id="f18da-133">МРН (идентификатор)</span><span class="sxs-lookup"><span data-stu-id="f18da-133">MRN (Identifier)</span></span>

<span data-ttu-id="f18da-134">В дополнение к [полям аргонаут](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="f18da-134">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="f18da-135">Name. use</span><span class="sxs-lookup"><span data-stu-id="f18da-135">Name.Use</span></span>
2. <span data-ttu-id="f18da-136">Name. prefix</span><span class="sxs-lookup"><span data-stu-id="f18da-136">Name.Prefix</span></span>
3. <span data-ttu-id="f18da-137">[Женералпрактитионер]-ссылка Женералпрактитионер должна включаться в ресурс пациент (только для отображения поля)</span><span class="sxs-lookup"><span data-stu-id="f18da-137">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="f18da-138">Поиск ресурсов использует метод POST по адресу/Patient/_search и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f18da-138">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="f18da-139">номер</span><span class="sxs-lookup"><span data-stu-id="f18da-139">id</span></span>
2. <span data-ttu-id="f18da-140">Family = (Поиск всех пациентов, чье имя семейства не содержало значение)</span><span class="sxs-lookup"><span data-stu-id="f18da-140">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="f18da-141">заданный\<= подстрока></span><span class="sxs-lookup"><span data-stu-id="f18da-141">given=\<substring></span></span>
4. <span data-ttu-id="f18da-142">Дата рождения = (точное совпадение)</span><span class="sxs-lookup"><span data-stu-id="f18da-142">birthdate=(exact match)</span></span>
5. <span data-ttu-id="f18da-143">Gender = (значения являются одним из административных пола)</span><span class="sxs-lookup"><span data-stu-id="f18da-143">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="f18da-144">\_Count (максимальное количество возвращаемых результатов)</span><span class="sxs-lookup"><span data-stu-id="f18da-144">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="f18da-145">Ответ должен содержать общее количество записей, возвращенных в результате поиска, и \_счетчик будет использоваться патиентсапп, чтобы ограничить количество возвращаемых записей.</span><span class="sxs-lookup"><span data-stu-id="f18da-145">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="f18da-146">Идентификатор =\<МРН></span><span class="sxs-lookup"><span data-stu-id="f18da-146">identifier=\<mrn></span></span>

<span data-ttu-id="f18da-147">Цель — найти и отфильтровать пациента в пациент, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f18da-147">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="f18da-148">ID: это идентификатор ресурса, который содержит каждый ресурс в ФХИР.</span><span class="sxs-lookup"><span data-stu-id="f18da-148">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="f18da-149">МРН: фактический идентификатор пациента, который будет знать клиникал сотрудника.</span><span class="sxs-lookup"><span data-stu-id="f18da-149">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="f18da-150">Мы понимаем, что этот МРН основывается на типе идентификатора в ресурсе идентификатора в ФХИР.</span><span class="sxs-lookup"><span data-stu-id="f18da-150">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="f18da-151">Имя</span><span class="sxs-lookup"><span data-stu-id="f18da-151">Name</span></span>
- <span data-ttu-id="f18da-152">Рождения</span><span class="sxs-lookup"><span data-stu-id="f18da-152">Birthdate</span></span>

<span data-ttu-id="f18da-153">Посмотрите следующий пример звонка:</span><span class="sxs-lookup"><span data-stu-id="f18da-153">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="f18da-154">Запрос: POST <фхир-Server>/Patient/_search текст запроса: с указанным = Рус&Family = Black</span><span class="sxs-lookup"><span data-stu-id="f18da-154">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="f18da-155">Response: {"resourceType": "пакет", "идентификатор": <"пакет-ID>", "META": {"Ластупдатед": "2019-01-14T23:44:45.052 + 00:00"}; "тип": ",", "всего", "ссылка": [{"отношение": "Self", "URL": <фхир-Server>/Patient/_search "}]," Entry ": [{" Фуллурл ": <фхир-Server>/патиент/<пациент-ID>", "ресурс": {"resourceType": "пациент"; "идентификатор": "Patient-ID>"; "ластупдатед": ",", <",", ":" 2017 – 10-18T18:32:37.000 + 00:00 "}," текст ": {" состояние ":" создано "," div ":"</span><span class="sxs-lookup"><span data-stu-id="f18da-155">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="f18da-156">символ</span><span class="sxs-lookup"><span data-stu-id="f18da-156">\n</span></span>        <p><span data-ttu-id="f18da-157">Рус Черное</span><span class="sxs-lookup"><span data-stu-id="f18da-157">Ruth Black</span></span></p><span data-ttu-id="f18da-158">символ</span><span class="sxs-lookup"><span data-stu-id="f18da-158">\n</span></span>      </div><span data-ttu-id="f18da-159">"}," идентификатор ": [{" использование ":" обычный "," тип ": {" программирование ": [{" System ":"http://hl7.org/fhir/v2/0203";" код ":" MR "," "," "," ",", "", "", "", "", "", "") "," система "http://hospital.smarthealthit.org1234567:", "," Name ": [{" use ":" официальный "," семья ":" Black ",", "," с "," с "," C "".</span><span class="sxs-lookup"><span data-stu-id="f18da-159">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="f18da-160">]}], "коммуникационное": [{"System": "Phone", "value": "800-599-2739"; "использовать": "Главная"}, {"система": "Телефон", "значение": "800-808-7785", "использование": ",", ",", ",", ",", ",", "Ruth.Black@example.com"}, "пола": "женщина", "Дата и значение" 1951-08-23 адрес ": [{": "Главная", "строка": ["26 Южная Рдапт 22"]; "город": "ОК", "74066 индекс": "USA"}]}, "Поиск": {"функция поиска", "по": "</span><span class="sxs-lookup"><span data-stu-id="f18da-160">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="f18da-161">Запрос: получение <фхир-Server>/патиент/<пациент-ID></span><span class="sxs-lookup"><span data-stu-id="f18da-161">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="f18da-162">Response: {"resourceType": "Patient", "идентификатор": <"Patient-ID>", "идентификатор": [{"использование": "обычное", "тип": {"http://hl7.org/fhir/v2/0203,", ",", ",": ",", "," "," "," ")", "имя": [{"использовать": "официальный", "1234567 Семья ":" Адамова извлекла "," с указанным ": [" Дэниел ";" X. "</span><span class="sxs-lookup"><span data-stu-id="f18da-162">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="f18da-163">]}], "пола": "папа", "ДеньРождения": "1925-12-23";}</span><span class="sxs-lookup"><span data-stu-id="f18da-163">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="f18da-164">Дополнительные [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="f18da-164">See [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="f18da-165">Наблюдение</span><span class="sxs-lookup"><span data-stu-id="f18da-165">Observation</span></span>

<span data-ttu-id="f18da-166">Это минимальные обязательные поля, которые являются подмножеством профиля с [важнейшими знаками аргонаут](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span><span class="sxs-lookup"><span data-stu-id="f18da-166">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="f18da-167">Эффективная (Дата и время)</span><span class="sxs-lookup"><span data-stu-id="f18da-167">Effective (date time or period)</span></span>
2. <span data-ttu-id="f18da-168">Код. кодирование. Code</span><span class="sxs-lookup"><span data-stu-id="f18da-168">Code.Coding.Code</span></span>
3. <span data-ttu-id="f18da-169">Валуекуантити. Value</span><span class="sxs-lookup"><span data-stu-id="f18da-169">ValueQuantity.Value</span></span>

<span data-ttu-id="f18da-170">В дополнение к полям Аргонаут для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="f18da-170">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="f18da-171">Код. программирование. Display</span><span class="sxs-lookup"><span data-stu-id="f18da-171">Code.Coding.Display</span></span>
2. <span data-ttu-id="f18da-172">Валуекуантити. ед.</span><span class="sxs-lookup"><span data-stu-id="f18da-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="f18da-173">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f18da-173">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="f18da-174">пациент =\<patient ID></span><span class="sxs-lookup"><span data-stu-id="f18da-174">patient=\<patient id></span></span>
2. <span data-ttu-id="f18da-175">_sort =-Дата</span><span class="sxs-lookup"><span data-stu-id="f18da-175">_sort=-date</span></span>
3. <span data-ttu-id="f18da-176">Category (мы будем запрашивать "Category =", чтобы получить список важных знаков.</span><span class="sxs-lookup"><span data-stu-id="f18da-176">category (we will query for “category=vital-signs”) to retrieve the list of vital signs.</span></span>

<span data-ttu-id="f18da-177">Ниже приведен пример звонка.</span><span class="sxs-lookup"><span data-stu-id="f18da-177">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="f18da-178">Запрос: GET <фхир-Server>/Обсерватион? пациент =<пациент-ID>&Категория = важнейшие знаки</span><span class="sxs-lookup"><span data-stu-id="f18da-178">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="f18da-179">Response: {"resourceType": "пакет", "идентификатор": "<-ID>", "тип": "набор поиска", "Итого": [{"ресурс": {"элемент": "<ресурсов", "", "" Категория ": [{" кодировка> ": [{" система ":"http://hl7.org/fhir/observation-category"," код ".) важные-"}],}]," код ": {" программирование ": [{" System ":"http://loinc.org"," код ":" 8867-4 ";" Показать ":" heart_rate "}]}," еффективедатетиме ":" 2009-04-08T00:00:00-06:00 "," валуекуантити ": {" value ": 72,0;" единица ":" {ритм} минуту "," система ":"http://unitsofmeasure.org",}},.</span><span class="sxs-lookup"><span data-stu-id="f18da-179">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "http://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="f18da-180">.</span><span class="sxs-lookup"><span data-stu-id="f18da-180"></span></span>
        <span data-ttu-id="f18da-181">.</span><span class="sxs-lookup"><span data-stu-id="f18da-181"></span></span>
      <span data-ttu-id="f18da-182">] }</span><span class="sxs-lookup"><span data-stu-id="f18da-182"></span></span>

* * *

<span data-ttu-id="f18da-183">Дополнительные [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="f18da-183">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="f18da-184">Условие</span><span class="sxs-lookup"><span data-stu-id="f18da-184">Condition</span></span>

<span data-ttu-id="f18da-185">Ниже приведено минимально необходимое поле, которое является подмножеством [профиля условия аргонаут](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span><span class="sxs-lookup"><span data-stu-id="f18da-185">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="f18da-186">Код. кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="f18da-186">Code.Coding[0].Display</span></span>

<span data-ttu-id="f18da-187">В дополнение к полям Аргонаут для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="f18da-187">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="f18da-188">ассертеддате</span><span class="sxs-lookup"><span data-stu-id="f18da-188">AssertedDate</span></span>
2. <span data-ttu-id="f18da-189">Уровню серьезности</span><span class="sxs-lookup"><span data-stu-id="f18da-189">Severity</span></span>

<span data-ttu-id="f18da-190">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f18da-190">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="f18da-191">пациент =\<patient ID></span><span class="sxs-lookup"><span data-stu-id="f18da-191">patient=\<patient id></span></span>
2. <span data-ttu-id="f18da-192">_Count =\<максимальное число результатов></span><span class="sxs-lookup"><span data-stu-id="f18da-192">_count=\<max results></span></span>

<span data-ttu-id="f18da-193">Ниже приведен пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="f18da-193">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="f18da-194">Запрос: GET <фхир-Server>/Кондитион? пациент =<пациент-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="f18da-194">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="f18da-195">Response: {"resourceType": "пакет", "идентификатор": <"пакет-ID>", "введите": "тип поиска", "Итого": 2, "элемент": [{"ресурс": {"resourceType": "условие", "идентификатор": "<ресурс-идентификатор>"; код ": {" Code ": [{" System "http://snomed.info/sct" "," код ":" 185903001 ";" Display ":" требуется инфлуенза иммунизатион ",}]}," важность ": {" программирование ": [{" System ":"http://snomed.info/sct"," код ":" 24484000 ";" Display ":" серьезный "}]}," ассертеддате ":" 2018-04-04 "}}.</span><span class="sxs-lookup"><span data-stu-id="f18da-195">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="f18da-196">.</span><span class="sxs-lookup"><span data-stu-id="f18da-196"></span></span>
        <span data-ttu-id="f18da-197">.</span><span class="sxs-lookup"><span data-stu-id="f18da-197"></span></span>
      <span data-ttu-id="f18da-198">] }</span><span class="sxs-lookup"><span data-stu-id="f18da-198"></span></span>

* * *
<span data-ttu-id="f18da-199">Дополнительные [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="f18da-199">See [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="f18da-200">Происходит</span><span class="sxs-lookup"><span data-stu-id="f18da-200">Encounter</span></span>

<span data-ttu-id="f18da-201">Это минимальные обязательные поля, которые являются подмножеством подмножества [основного профиля](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) , которое должно иметь "поля".</span><span class="sxs-lookup"><span data-stu-id="f18da-201">These are the minimum required fields, which are a subset of the [US Core Encounter profile](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) “must have” fields).</span></span>

1. <span data-ttu-id="f18da-202">Состояни</span><span class="sxs-lookup"><span data-stu-id="f18da-202">Status</span></span>
2. <span data-ttu-id="f18da-203">Введите [0]. Кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="f18da-203">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="f18da-204">Кроме того, ниже перечислены поля, которые можно получить из основных полей "требуется поддержка" для профиля в США.</span><span class="sxs-lookup"><span data-stu-id="f18da-204">In addition, the following fields from US Core Encounter profile’s “must support” fields:</span></span>

1. <span data-ttu-id="f18da-205">Period. Start</span><span class="sxs-lookup"><span data-stu-id="f18da-205">Period.Start</span></span>
2. <span data-ttu-id="f18da-206">Расположение [0]. Расположение. Display</span><span class="sxs-lookup"><span data-stu-id="f18da-206">Location[0].Location.Display</span></span>

<span data-ttu-id="f18da-207">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f18da-207">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="f18da-208">пациент =\<patient ID></span><span class="sxs-lookup"><span data-stu-id="f18da-208">patient=\<patient id></span></span>
2. <span data-ttu-id="f18da-209">_sort: DESC =\<Field ex.</span><span class="sxs-lookup"><span data-stu-id="f18da-209">_sort:desc=\<field ex.</span></span> <span data-ttu-id="f18da-210">Дата></span><span class="sxs-lookup"><span data-stu-id="f18da-210">date></span></span>
3. <span data-ttu-id="f18da-211">_Count =\<максимальное число результатов></span><span class="sxs-lookup"><span data-stu-id="f18da-211">_count=\<max results></span></span>

<span data-ttu-id="f18da-212">Цель — получить Последнее известное расположение пациента.</span><span class="sxs-lookup"><span data-stu-id="f18da-212">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="f18da-213">Каждый из этих обнаружений ссылается на ресурс расположения.</span><span class="sxs-lookup"><span data-stu-id="f18da-213">Each encounter references a location resource.</span></span> <span data-ttu-id="f18da-214">Ссылка также должна включать поле отображения местоположения.</span><span class="sxs-lookup"><span data-stu-id="f18da-214">The reference shall also include the location’s display field.</span></span>

<span data-ttu-id="f18da-215">Дополнительные [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="f18da-215">See [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="f18da-216">аллергинтолеранце</span><span class="sxs-lookup"><span data-stu-id="f18da-216">AllergyIntolerance</span></span>

<span data-ttu-id="f18da-217">Это минимальные обязательные поля, которые являются подмножеством профиля [Аргонаут аллергинтолеранце](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :</span><span class="sxs-lookup"><span data-stu-id="f18da-217">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="f18da-218">Code. Text</span><span class="sxs-lookup"><span data-stu-id="f18da-218">Code.Text</span></span>
2. <span data-ttu-id="f18da-219">Код. кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="f18da-219">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="f18da-220">Клиникалстатус/Верификатионстатус (мы прочитали оба)</span><span class="sxs-lookup"><span data-stu-id="f18da-220">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="f18da-221">В дополнение к полям Аргонаут для удобства пользователей приложение пациентов также может прочитать следующее поле:</span><span class="sxs-lookup"><span data-stu-id="f18da-221">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="f18da-222">ассертеддате</span><span class="sxs-lookup"><span data-stu-id="f18da-222">AssertedDate</span></span>
2. <span data-ttu-id="f18da-223">Примечание. текст</span><span class="sxs-lookup"><span data-stu-id="f18da-223">Note.Text</span></span>
3. <span data-ttu-id="f18da-224">Реакция</span><span class="sxs-lookup"><span data-stu-id="f18da-224">Reaction</span></span>
    1. <span data-ttu-id="f18da-225">Вещество (один элемент кодирования)</span><span class="sxs-lookup"><span data-stu-id="f18da-225">Substance (one coding element)</span></span>
    2. <span data-ttu-id="f18da-226">Манифест (один элемент кодирования)</span><span class="sxs-lookup"><span data-stu-id="f18da-226">Manifestation (one coding element)</span></span>

<span data-ttu-id="f18da-227">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f18da-227">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="f18da-228">Пациент = \<patient ID></span><span class="sxs-lookup"><span data-stu-id="f18da-228">Patient =  \<patient id></span></span>

<span data-ttu-id="f18da-229">Посмотрите следующий пример звонка:</span><span class="sxs-lookup"><span data-stu-id="f18da-229">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="f18da-230">Запрос: GET <фхир-Server>/Аллергинтолеранце? пациент =<пациент-ID></span><span class="sxs-lookup"><span data-stu-id="f18da-230">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="f18da-231">Ответ: {"resourceType": "пакет", "идентификатор": "<пакета-ID>", "тип": "набор поиска", "Итого": {",", ",": [{"ресурс", "Аллергинтолеранце", "идентификатор": "<Resource-id>", "Клиникалстатус": "Active" Рификатионстатус ":" подтверждено "," код ": {"http://rxnav.nlm.nih.gov/REST/Ndfrt, "," код ":" N0000175503 "," Display ":" сулфонамиде ",}]," текст ":" сулфонамиде АНТ ибактериал "};" Ассертеддате ":" 2018-01-01T00:00:00-07:00 ";" реакция ": [{", "," ", код": [{"System": "http://snomed.info/sct  "271807003"; "Показать": "Skin Раш",}], "текст": "Skin Раш"}],}]}}]}</span><span class="sxs-lookup"><span data-stu-id="f18da-231">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="f18da-232">Дополнительные [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="f18da-232">See [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="f18da-233">Запрос лечения</span><span class="sxs-lookup"><span data-stu-id="f18da-233">Medication Request</span></span>

<span data-ttu-id="f18da-234">Ниже указаны минимальные обязательные поля, которые являются подмножеством [профиля запроса "основной лечения" США](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html).</span><span class="sxs-lookup"><span data-stu-id="f18da-234">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="f18da-235">Лечения. Display (если ссылка)</span><span class="sxs-lookup"><span data-stu-id="f18da-235">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="f18da-236">Лечения. Text (если Кодаблеконцепт)</span><span class="sxs-lookup"><span data-stu-id="f18da-236">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="f18da-237">аусоредон</span><span class="sxs-lookup"><span data-stu-id="f18da-237">AuthoredOn</span></span>
4. <span data-ttu-id="f18da-238">Запросивший. агент. Display</span><span class="sxs-lookup"><span data-stu-id="f18da-238">Requester.Agent.Display</span></span>

<span data-ttu-id="f18da-239">В дополнение к полям "основные" в США для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="f18da-239">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="f18da-240">Досажеинструктион [..]. Текстовые</span><span class="sxs-lookup"><span data-stu-id="f18da-240">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="f18da-241">Текстовые</span><span class="sxs-lookup"><span data-stu-id="f18da-241">Text</span></span>

<span data-ttu-id="f18da-242">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f18da-242">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="f18da-243">пациент =\<patient ID></span><span class="sxs-lookup"><span data-stu-id="f18da-243">patient=\<patient id></span></span>
2. <span data-ttu-id="f18da-244">_Count =\<максимальное число результатов></span><span class="sxs-lookup"><span data-stu-id="f18da-244">_count=\<max results></span></span>

<span data-ttu-id="f18da-245">Дополнительные [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="f18da-245">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="f18da-246">Приложения</span><span class="sxs-lookup"><span data-stu-id="f18da-246">Coverage</span></span>

<span data-ttu-id="f18da-247">Это минимальный обязательный набор полей, не охваченных профилями США или Аргонаут:</span><span class="sxs-lookup"><span data-stu-id="f18da-247">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="f18da-248">Группировка, по крайней мере один элемент с</span><span class="sxs-lookup"><span data-stu-id="f18da-248">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="f18da-249">граупдисплай</span><span class="sxs-lookup"><span data-stu-id="f18da-249">GroupDisplay</span></span>
    2. <span data-ttu-id="f18da-250">пландисплай</span><span class="sxs-lookup"><span data-stu-id="f18da-250">PlanDisplay</span></span>
2. <span data-ttu-id="f18da-251">Срока</span><span class="sxs-lookup"><span data-stu-id="f18da-251">Period</span></span>
3. <span data-ttu-id="f18da-252">субскриберид</span><span class="sxs-lookup"><span data-stu-id="f18da-252">SubscriberId</span></span>

<span data-ttu-id="f18da-253">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f18da-253">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="f18da-254">Пациент = \<patient ID></span><span class="sxs-lookup"><span data-stu-id="f18da-254">Patient = \<patient id></span></span>

<span data-ttu-id="f18da-255">Дополнительные [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="f18da-255">See [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
