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
ms.openlocfilehash: bcae5b6fae3da469aaaa35b3a0494273fa8d29ba
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277213"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="c8acf-103">Характеристики интерфейса STU3</span><span class="sxs-lookup"><span data-stu-id="c8acf-103">STU3 interface specification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8acf-104">**Действующий 30 сентября 2020 г. приложение пациентов будет признано устаревшим, и пользователи больше не смогут установить его из магазина App Store. Мы рекомендуем вам приступить к работе с [приложением "списки](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) " в Teams уже сегодня.**</span><span class="sxs-lookup"><span data-stu-id="c8acf-104">**Effective September 30, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="c8acf-105">Данные приложения пациентов хранятся в почтовом ящике группы Office 365, которая является резервной командой.</span><span class="sxs-lookup"><span data-stu-id="c8acf-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="c8acf-106">Когда приложение пациентов удаляется, все связанные с ним данные будут храниться в этой группе, но к нему больше нельзя будет получить доступ с помощью пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c8acf-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="c8acf-107">Текущие пользователи могут повторно создавать свои списки с помощью [приложения "списки](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)".</span><span class="sxs-lookup"><span data-stu-id="c8acf-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="c8acf-108">[Приложение "списки](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) " предустановлено для всех пользователей Teams и доступно в виде вкладки в каждой команде и канале.</span><span class="sxs-lookup"><span data-stu-id="c8acf-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="c8acf-109">С помощью списков благодаря специалистам по карьерным тарифам могут создаваться списки пациента с использованием встроенного шаблона пациентов, с нуля или путем импорта данных в Excel.</span><span class="sxs-lookup"><span data-stu-id="c8acf-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="c8acf-110">Дополнительные сведения об управлении приложением Lists в Организации можно найти в разделе [Управление приложением "списки"](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="c8acf-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="c8acf-111">Настройка или перенастройка сервера FHIR для работы с приложением Microsoft Teams пациентов требует понимания данных, к которым приложению требуется доступ.</span><span class="sxs-lookup"><span data-stu-id="c8acf-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="c8acf-112">Сервер FHIR должен поддерживать запросы POST, используя пакеты для указанных ниже ресурсов.</span><span class="sxs-lookup"><span data-stu-id="c8acf-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="c8acf-113">Подождите</span><span class="sxs-lookup"><span data-stu-id="c8acf-113">Patient</span></span>](#patient)
- [<span data-ttu-id="c8acf-114">Наблюдение</span><span class="sxs-lookup"><span data-stu-id="c8acf-114">Observation</span></span>](#observation)
- [<span data-ttu-id="c8acf-115">Условие</span><span class="sxs-lookup"><span data-stu-id="c8acf-115">Condition</span></span>](#condition)
- [<span data-ttu-id="c8acf-116">Происходит</span><span class="sxs-lookup"><span data-stu-id="c8acf-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="c8acf-117">Недопустимый Allergy</span><span class="sxs-lookup"><span data-stu-id="c8acf-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="c8acf-118">Приложения</span><span class="sxs-lookup"><span data-stu-id="c8acf-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="c8acf-119">[Оператор лечения](#medication-request) (заменяет MEDICATIONORDER в DSTU2 версии PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="c8acf-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="c8acf-120">Расположение (данные, необходимые для этого ресурса, могут быть включены в план)</span><span class="sxs-lookup"><span data-stu-id="c8acf-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="c8acf-121">Ресурс пациент является единственным обязательным ресурсом (без которого приложение не будет загружаться вообще); Тем не менее, рекомендуется, чтобы партнеры реализовали поддержку всех вышеупомянутых ресурсов для спецификаций, указанных ниже, для наилучшего взаимодействия с пользователем в приложении Microsoft Teams пациентов.</span><span class="sxs-lookup"><span data-stu-id="c8acf-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="c8acf-122">Запросы из приложения Microsoft Teams пациентов для более чем одного ресурса должны публиковать набор (пакет) запросов на URL-адрес сервера FHIR.</span><span class="sxs-lookup"><span data-stu-id="c8acf-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="c8acf-123">Сервер должен обрабатывать каждый запрос и возвращать набор ресурсов, соответствующих каждому запросу.</span><span class="sxs-lookup"><span data-stu-id="c8acf-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="c8acf-124">Дополнительные сведения и примеры можно найти в разделе [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="c8acf-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="c8acf-125">Оператор возможностей</span><span class="sxs-lookup"><span data-stu-id="c8acf-125">Capability Statement</span></span>

<span data-ttu-id="c8acf-126">Ниже указаны минимальные обязательные поля.</span><span class="sxs-lookup"><span data-stu-id="c8acf-126">These are the minimum required fields:</span></span>

1. <span data-ttu-id="c8acf-127">ДЕРЖИВАЕТ</span><span class="sxs-lookup"><span data-stu-id="c8acf-127">REST</span></span>
   1. <span data-ttu-id="c8acf-128">Режиме</span><span class="sxs-lookup"><span data-stu-id="c8acf-128">Mode</span></span>
   2. <span data-ttu-id="c8acf-129">Действует</span><span class="sxs-lookup"><span data-stu-id="c8acf-129">Interaction</span></span>
   3. <span data-ttu-id="c8acf-130">Ресурс: тип</span><span class="sxs-lookup"><span data-stu-id="c8acf-130">Resource: Type</span></span>
   4. <span data-ttu-id="c8acf-131">Безопасность: [расширение URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="c8acf-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="c8acf-132">FhirVersion (для нашего кода требуется, чтобы узнать, в какую версию следует поворачивать.)</span><span class="sxs-lookup"><span data-stu-id="c8acf-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="c8acf-133">[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="c8acf-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="c8acf-134">Подождите</span><span class="sxs-lookup"><span data-stu-id="c8acf-134">Patient</span></span>

<span data-ttu-id="c8acf-135">Ниже приведены минимальные обязательные поля, которые являются подмножеством полей профиля пациента Argonaut:</span><span class="sxs-lookup"><span data-stu-id="c8acf-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="c8acf-136">Name (имя). задано</span><span class="sxs-lookup"><span data-stu-id="c8acf-136">Name.Given</span></span>
2. <span data-ttu-id="c8acf-137">Family (имя)</span><span class="sxs-lookup"><span data-stu-id="c8acf-137">Name.Family</span></span>
3. <span data-ttu-id="c8acf-138">Полу</span><span class="sxs-lookup"><span data-stu-id="c8acf-138">Gender</span></span>
4. <span data-ttu-id="c8acf-139">Рождения</span><span class="sxs-lookup"><span data-stu-id="c8acf-139">BirthDate</span></span>
5. <span data-ttu-id="c8acf-140">MRN (идентификатор)</span><span class="sxs-lookup"><span data-stu-id="c8acf-140">MRN (Identifier)</span></span>

<span data-ttu-id="c8acf-141">В дополнение к [полям Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="c8acf-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="c8acf-142">Name. use</span><span class="sxs-lookup"><span data-stu-id="c8acf-142">Name.Use</span></span>
2. <span data-ttu-id="c8acf-143">Name. prefix</span><span class="sxs-lookup"><span data-stu-id="c8acf-143">Name.Prefix</span></span>
3. <span data-ttu-id="c8acf-144">[GeneralPractitioner]-ссылка GeneralPractitioner должна включаться в ресурс пациент (только для отображения поля)</span><span class="sxs-lookup"><span data-stu-id="c8acf-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="c8acf-145">Поиск ресурсов использует метод POST по адресу/Patient/_search и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="c8acf-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="c8acf-146">номер</span><span class="sxs-lookup"><span data-stu-id="c8acf-146">id</span></span>
2. <span data-ttu-id="c8acf-147">Family = (Поиск всех пациентов, чье имя семейства не содержало значение)</span><span class="sxs-lookup"><span data-stu-id="c8acf-147">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="c8acf-148">указанный =\<substring></span><span class="sxs-lookup"><span data-stu-id="c8acf-148">given=\<substring></span></span>
4. <span data-ttu-id="c8acf-149">Дата рождения = (точное совпадение)</span><span class="sxs-lookup"><span data-stu-id="c8acf-149">birthdate=(exact match)</span></span>
5. <span data-ttu-id="c8acf-150">Gender = (значения являются одним из административных пола)</span><span class="sxs-lookup"><span data-stu-id="c8acf-150">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="c8acf-151">\_Count (максимальное количество возвращаемых результатов)</span><span class="sxs-lookup"><span data-stu-id="c8acf-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="c8acf-152">Ответ должен содержать общее количество записей, возвращенных в результате поиска, и \_ счетчик будет использоваться PatientsApp, чтобы ограничить количество возвращаемых записей.</span><span class="sxs-lookup"><span data-stu-id="c8acf-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="c8acf-153">Идентификатор =\<mrn></span><span class="sxs-lookup"><span data-stu-id="c8acf-153">identifier=\<mrn></span></span>

<span data-ttu-id="c8acf-154">Цель — найти и отфильтровать пациента в пациент, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="c8acf-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="c8acf-155">ID: это идентификатор ресурса, который содержит каждый ресурс в FHIR.</span><span class="sxs-lookup"><span data-stu-id="c8acf-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="c8acf-156">MRN: фактический идентификатор пациента, который будет знать Clinical сотрудника.</span><span class="sxs-lookup"><span data-stu-id="c8acf-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="c8acf-157">Мы понимаем, что этот MRN основывается на типе идентификатора в ресурсе идентификатора в FHIR.</span><span class="sxs-lookup"><span data-stu-id="c8acf-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="c8acf-158">Имя</span><span class="sxs-lookup"><span data-stu-id="c8acf-158">Name</span></span>
- <span data-ttu-id="c8acf-159">Рождения</span><span class="sxs-lookup"><span data-stu-id="c8acf-159">Birthdate</span></span>

<span data-ttu-id="c8acf-160">Посмотрите следующий пример звонка:</span><span class="sxs-lookup"><span data-stu-id="c8acf-160">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="c8acf-161">Запрос: POST <fhir-Server>/Patient/_search запроса: с указанным = Ruth&Family = Black</span><span class="sxs-lookup"><span data-stu-id="c8acf-161">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="c8acf-162">Response: {"resourceType": "пакет", "идентификатор": <"пакет-ID>", "META": {"lastUpdated": "2019-01-14T23:44:45.052 + 00:00", "тип": ",", "всего", "ссылка": [{"отношение": "Self", "URL": <fhir-Server>/Patient/_search "}]," запись ". [{" fullUrl ": <fhir-Server>/Patient/<пациент-ID>", "ресурс": {"resourceType": "Patient", "ИД": "<пациент-ID>", "META": {«versionId»: «1», «lastUpdated»: «2017-10-18T18:32:37.000 + 00:00»}, «текст»: «создано», «div»: «</span><span class="sxs-lookup"><span data-stu-id="c8acf-162">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="c8acf-163">символ</span><span class="sxs-lookup"><span data-stu-id="c8acf-163">\n</span></span>        <p><span data-ttu-id="c8acf-164">Ruth Черное</span><span class="sxs-lookup"><span data-stu-id="c8acf-164">Ruth Black</span></span></p><span data-ttu-id="c8acf-165">символ</span><span class="sxs-lookup"><span data-stu-id="c8acf-165">\n</span></span>      </div><span data-ttu-id="c8acf-166">"}," идентификатор ": [{" использование ":" обычное "," тип ": {" код ": [{" System ":" https://hl7.org/fhir/v2/0203 "," Code ":" MR "," Display ":" номер медицинские записи "," userSelected ": false}];" текст ":", "," "система": ",", ",", ",", ",", "-", "," ","-",", ",": http://hospital.smarthealthit.org ["Ruth", "C". 1234567</span><span class="sxs-lookup"><span data-stu-id="c8acf-166">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="c8acf-167">]}], "телекоммуникационной": [{"система": "Телефон", "значение": "800-599-2739", "использовать": "Главная"}, "использовать": ",", 800-808-7785 ",", ",", ",", ",", ",", ",", ",", ",". женщина "," ДеньРождения ":" 1951-08-23 "," адрес ": [{" использование ":" Главная "," строка ": [" 26-Южный RdApt 22 "]," город ":" Sapulpa "" состояние ":" ОК "," postalCode ":" 74066 "," страна ":" USA "}]}," Поиск ": {" Мода ":" Match "}}]}</span><span class="sxs-lookup"><span data-stu-id="c8acf-167">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="c8acf-168">Запрос: получение <fhir-Server>/Patient/<пациент-ID></span><span class="sxs-lookup"><span data-stu-id="c8acf-168">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="c8acf-169">Response: {"resourceType": "пациент"; "идентификатор": <"Patient-ID>", "идентификатор": [{"использование": "обычно", "тип": {"программирование": [{"System": " https://hl7.org/fhir/v2/0203 ", "код": "MR",}], "текст": "номер медицинские записи"}, "имя": [{"использование": "официальный", "семья": "Адамова извлекла", "заданный": ["Дэниел", "X." 1234567</span><span class="sxs-lookup"><span data-stu-id="c8acf-169">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="c8acf-170">]}], "пола": "папа", "ДеньРождения": "1925-12-23";}</span><span class="sxs-lookup"><span data-stu-id="c8acf-170">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="c8acf-171">[https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="c8acf-171">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="c8acf-172">Наблюдение</span><span class="sxs-lookup"><span data-stu-id="c8acf-172">Observation</span></span>

<span data-ttu-id="c8acf-173">Это минимальные обязательные поля, которые являются подмножеством профиля с [важнейшими знаками Argonaut](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span><span class="sxs-lookup"><span data-stu-id="c8acf-173">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="c8acf-174">Эффективная (Дата и время)</span><span class="sxs-lookup"><span data-stu-id="c8acf-174">Effective (date time or period)</span></span>
2. <span data-ttu-id="c8acf-175">Код. кодирование. Code</span><span class="sxs-lookup"><span data-stu-id="c8acf-175">Code.Coding.Code</span></span>
3. <span data-ttu-id="c8acf-176">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="c8acf-176">ValueQuantity.Value</span></span>

<span data-ttu-id="c8acf-177">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="c8acf-177">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="c8acf-178">Код. программирование. Display</span><span class="sxs-lookup"><span data-stu-id="c8acf-178">Code.Coding.Display</span></span>
2. <span data-ttu-id="c8acf-179">ValueQuantity. ед.</span><span class="sxs-lookup"><span data-stu-id="c8acf-179">ValueQuantity.Unit</span></span>

<span data-ttu-id="c8acf-180">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="c8acf-180">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="c8acf-181">пациент =\<patient id></span><span class="sxs-lookup"><span data-stu-id="c8acf-181">patient=\<patient id></span></span>
2. <span data-ttu-id="c8acf-182">_sort =-Дата</span><span class="sxs-lookup"><span data-stu-id="c8acf-182">_sort=-date</span></span>
3. <span data-ttu-id="c8acf-183">Category (мы будем запрашивать "Category =", чтобы получить список важных знаков.</span><span class="sxs-lookup"><span data-stu-id="c8acf-183">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="c8acf-184">Ниже приведен пример звонка.</span><span class="sxs-lookup"><span data-stu-id="c8acf-184">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="c8acf-185">Запрос: GET <fhir-Server>/Observation? пациент =<пациент-ID>&Категория = важнейшие знаки</span><span class="sxs-lookup"><span data-stu-id="c8acf-185">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="c8acf-186">Response: {"resourceType": "пакет", "идентификатор": <"пакет-ID>", "тип": "тип поиска", "Итого": 20, "запись": [{"ресурс": {"ResourceType": "значение", "идентификатор": "<ресурсов-идентификаторы>"; "Категория": [{"System": "" https://hl7.org/fhir/observation-category , "" код ": {" программирование ": [{" System ":" ";" код ":" 8867-4 "," Display ":" effectiveDateTime "} http://loinc.org ]}," "...": "2009-04-08T00 heart_rate: 00:00-06:00"; "valueQuantity": {"значение": 72,0, "Unit": "{ритм} минуту"; "System": " http://unitsofmeasure.org ",}}}.</span><span class="sxs-lookup"><span data-stu-id="c8acf-186">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "https://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="c8acf-187">.</span><span class="sxs-lookup"><span data-stu-id="c8acf-187">.</span></span>
        <span data-ttu-id="c8acf-188">.</span><span class="sxs-lookup"><span data-stu-id="c8acf-188">.</span></span>
      <span data-ttu-id="c8acf-189">] }</span><span class="sxs-lookup"><span data-stu-id="c8acf-189">] }</span></span>

* * *

<span data-ttu-id="c8acf-190">[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="c8acf-190">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="c8acf-191">Условие</span><span class="sxs-lookup"><span data-stu-id="c8acf-191">Condition</span></span>

<span data-ttu-id="c8acf-192">Ниже приведено минимально необходимое поле, которое является подмножеством [профиля условия Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span><span class="sxs-lookup"><span data-stu-id="c8acf-192">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="c8acf-193">Код. кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="c8acf-193">Code.Coding[0].Display</span></span>

<span data-ttu-id="c8acf-194">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="c8acf-194">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="c8acf-195">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="c8acf-195">AssertedDate</span></span>
2. <span data-ttu-id="c8acf-196">Уровню серьезности</span><span class="sxs-lookup"><span data-stu-id="c8acf-196">Severity</span></span>

<span data-ttu-id="c8acf-197">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="c8acf-197">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="c8acf-198">пациент =\<patient id></span><span class="sxs-lookup"><span data-stu-id="c8acf-198">patient=\<patient id></span></span>
2. <span data-ttu-id="c8acf-199">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="c8acf-199">_count=\<max results></span></span>

<span data-ttu-id="c8acf-200">Ниже приведен пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="c8acf-200">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="c8acf-201">Запрос: GET <fhir-Server>/Condition? пациент =<пациент-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="c8acf-201">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="c8acf-202">Ответ: {"resourceType": "набор", "идентификатор": "<пакет-ID>"; "тип": "набор поиска", "всего", "элемент": [{"ресурс": {"ИД": "условие", "идентификатор": "<ресурс-идентификатор>", "код": {"программирование": [{"System": " http://snomed.info/sct ", "код": "185903001"; "вывод": "требуется influenza Immunization",}]}, "важность": {"Code": ",", ",": " http://snomed.info/sct 24484000"; "вывод": "серьезный"}]}, "assertedDate": "2018-04-04"}}</span><span class="sxs-lookup"><span data-stu-id="c8acf-202">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="c8acf-203">.</span><span class="sxs-lookup"><span data-stu-id="c8acf-203">.</span></span>
        <span data-ttu-id="c8acf-204">.</span><span class="sxs-lookup"><span data-stu-id="c8acf-204">.</span></span>
      <span data-ttu-id="c8acf-205">] }</span><span class="sxs-lookup"><span data-stu-id="c8acf-205">] }</span></span>

* * *
<span data-ttu-id="c8acf-206">[https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="c8acf-206">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="c8acf-207">Происходит</span><span class="sxs-lookup"><span data-stu-id="c8acf-207">Encounter</span></span>

<span data-ttu-id="c8acf-208">Это минимальные обязательные поля, которые являются подмножеством подмножества [основного профиля](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) , которое должно иметь "поля".</span><span class="sxs-lookup"><span data-stu-id="c8acf-208">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

1. <span data-ttu-id="c8acf-209">Состояни</span><span class="sxs-lookup"><span data-stu-id="c8acf-209">Status</span></span>
2. <span data-ttu-id="c8acf-210">Введите [0]. Кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="c8acf-210">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="c8acf-211">Кроме того, ниже перечислены поля, которые можно получить из основных полей "требуется поддержка" для профиля в США.</span><span class="sxs-lookup"><span data-stu-id="c8acf-211">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

1. <span data-ttu-id="c8acf-212">Period. Start</span><span class="sxs-lookup"><span data-stu-id="c8acf-212">Period.Start</span></span>
2. <span data-ttu-id="c8acf-213">Расположение [0]. Расположение. Display</span><span class="sxs-lookup"><span data-stu-id="c8acf-213">Location[0].Location.Display</span></span>

<span data-ttu-id="c8acf-214">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="c8acf-214">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="c8acf-215">пациент =\<patient id></span><span class="sxs-lookup"><span data-stu-id="c8acf-215">patient=\<patient id></span></span>
2. <span data-ttu-id="c8acf-216">_sort: DESC =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="c8acf-216">_sort:desc=\<field ex. date></span></span>
3. <span data-ttu-id="c8acf-217">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="c8acf-217">_count=\<max results></span></span>

<span data-ttu-id="c8acf-218">Цель — получить Последнее известное расположение пациента.</span><span class="sxs-lookup"><span data-stu-id="c8acf-218">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="c8acf-219">Каждый из этих обнаружений ссылается на ресурс расположения.</span><span class="sxs-lookup"><span data-stu-id="c8acf-219">Each encounter references a location resource.</span></span> <span data-ttu-id="c8acf-220">Ссылка также должна включать поле отображения местоположения.</span><span class="sxs-lookup"><span data-stu-id="c8acf-220">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="c8acf-221">[https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="c8acf-221">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="c8acf-222">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="c8acf-222">AllergyIntolerance</span></span>

<span data-ttu-id="c8acf-223">Это минимальные обязательные поля, которые являются подмножеством профиля [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :</span><span class="sxs-lookup"><span data-stu-id="c8acf-223">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="c8acf-224">Code. Text</span><span class="sxs-lookup"><span data-stu-id="c8acf-224">Code.Text</span></span>
2. <span data-ttu-id="c8acf-225">Код. кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="c8acf-225">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="c8acf-226">ClinicalStatus/VerificationStatus (мы прочитали оба)</span><span class="sxs-lookup"><span data-stu-id="c8acf-226">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="c8acf-227">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также может прочитать следующее поле:</span><span class="sxs-lookup"><span data-stu-id="c8acf-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="c8acf-228">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="c8acf-228">AssertedDate</span></span>
2. <span data-ttu-id="c8acf-229">Примечание. текст</span><span class="sxs-lookup"><span data-stu-id="c8acf-229">Note.Text</span></span>
3. <span data-ttu-id="c8acf-230">Реакция</span><span class="sxs-lookup"><span data-stu-id="c8acf-230">Reaction</span></span>
    1. <span data-ttu-id="c8acf-231">Вещество (один элемент кодирования)</span><span class="sxs-lookup"><span data-stu-id="c8acf-231">Substance (one coding element)</span></span>
    2. <span data-ttu-id="c8acf-232">Манифест (один элемент кодирования)</span><span class="sxs-lookup"><span data-stu-id="c8acf-232">Manifestation (one coding element)</span></span>

<span data-ttu-id="c8acf-233">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="c8acf-233">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="c8acf-234">Пациент =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="c8acf-234">Patient =  \<patient id></span></span>

<span data-ttu-id="c8acf-235">Посмотрите следующий пример звонка:</span><span class="sxs-lookup"><span data-stu-id="c8acf-235">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="c8acf-236">Запрос: GET <fhir-Server>/AllergyIntolerance? пациент =<пациент-ID></span><span class="sxs-lookup"><span data-stu-id="c8acf-236">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="c8acf-237">Response: {"resourceType": "пакет", "идентификатор": <"набор-ID>", "тип": "набор результатов", "Total": 1, "запись": [{"ресурс": {"resourceType": "AllergyIntolerance"; "идентификатор": "clinicalStatus": ",", "verificationStatus": "утверждено", "код": ",": ",".> <http://rxnav.nlm.nih.gov/REST/Ndfrt N0000175503 "," Display ":" sulfonamide ",}]," текст ":" sulfonamide ","} "," assertedDate ":" 2018-01-01T00:00:00-07:00 "," реакция ": [манифест": [{"программирование": [{"System": ""; "код": "271807003"; http://snomed.info/sct "отобразить": "Skin RASH",}], "текст": "Skin RASH"}],}]}}]}</span><span class="sxs-lookup"><span data-stu-id="c8acf-237">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="c8acf-238">[https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="c8acf-238">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="c8acf-239">Запрос лечения</span><span class="sxs-lookup"><span data-stu-id="c8acf-239">Medication Request</span></span>

<span data-ttu-id="c8acf-240">Ниже указаны минимальные обязательные поля, которые являются подмножеством [профиля запроса "основной лечения" США](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html).</span><span class="sxs-lookup"><span data-stu-id="c8acf-240">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="c8acf-241">Лечения. Display (если ссылка)</span><span class="sxs-lookup"><span data-stu-id="c8acf-241">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="c8acf-242">Лечения. Text (если CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="c8acf-242">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="c8acf-243">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="c8acf-243">AuthoredOn</span></span>
4. <span data-ttu-id="c8acf-244">Запросивший. агент. Display</span><span class="sxs-lookup"><span data-stu-id="c8acf-244">Requester.Agent.Display</span></span>

<span data-ttu-id="c8acf-245">В дополнение к полям "основные" в США для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="c8acf-245">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="c8acf-246">DosageInstruction[..]. Текстовые</span><span class="sxs-lookup"><span data-stu-id="c8acf-246">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="c8acf-247">Текстовые</span><span class="sxs-lookup"><span data-stu-id="c8acf-247">Text</span></span>

<span data-ttu-id="c8acf-248">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="c8acf-248">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="c8acf-249">пациент =\<patient id></span><span class="sxs-lookup"><span data-stu-id="c8acf-249">patient=\<patient id></span></span>
2. <span data-ttu-id="c8acf-250">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="c8acf-250">_count=\<max results></span></span>

<span data-ttu-id="c8acf-251">[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="c8acf-251">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="c8acf-252">Приложения</span><span class="sxs-lookup"><span data-stu-id="c8acf-252">Coverage</span></span>

<span data-ttu-id="c8acf-253">Это минимальный обязательный набор полей, не охваченных профилями США или Argonaut:</span><span class="sxs-lookup"><span data-stu-id="c8acf-253">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="c8acf-254">Группировка, по крайней мере один элемент с</span><span class="sxs-lookup"><span data-stu-id="c8acf-254">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="c8acf-255">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="c8acf-255">GroupDisplay</span></span>
    2. <span data-ttu-id="c8acf-256">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="c8acf-256">PlanDisplay</span></span>
2. <span data-ttu-id="c8acf-257">Срока</span><span class="sxs-lookup"><span data-stu-id="c8acf-257">Period</span></span>
3. <span data-ttu-id="c8acf-258">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="c8acf-258">SubscriberId</span></span>

<span data-ttu-id="c8acf-259">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="c8acf-259">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="c8acf-260">Пациент = \<patient id></span><span class="sxs-lookup"><span data-stu-id="c8acf-260">Patient = \<patient id></span></span>

<span data-ttu-id="c8acf-261">[https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="c8acf-261">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
