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
ms.openlocfilehash: 2fa5575d6d7a4cbdffec6c3396004c38e743720a
ms.sourcegitcommit: 3b54a56ec1fe4366580621e19cdbb6a833a01161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361459"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="974f0-103">Характеристики интерфейса DSTU2</span><span class="sxs-lookup"><span data-stu-id="974f0-103">DSTU2 interface specification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="974f0-104">**Эффективная работа с 15 октября 2020 г. приложение пациентов будет устаревшим, и пользователи больше не смогут установить его из магазина приложений Teams. Мы рекомендуем вам приступить к работе с [приложением "списки](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) " в Teams уже сегодня.**</span><span class="sxs-lookup"><span data-stu-id="974f0-104">**Effective October 15, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="974f0-105">Данные приложения пациентов хранятся в почтовом ящике группы Office 365, которая является резервной командой.</span><span class="sxs-lookup"><span data-stu-id="974f0-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="974f0-106">Когда приложение пациентов удаляется, все связанные с ним данные будут храниться в этой группе, но к нему больше нельзя будет получить доступ с помощью пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="974f0-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="974f0-107">Текущие пользователи могут повторно создавать свои списки с помощью [приложения "списки](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)".</span><span class="sxs-lookup"><span data-stu-id="974f0-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="974f0-108">[Приложение "списки](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) " предустановлено для всех пользователей Teams и доступно в виде вкладки в каждой команде и канале.</span><span class="sxs-lookup"><span data-stu-id="974f0-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="974f0-109">С помощью списков благодаря специалистам по карьерным тарифам могут создаваться списки пациента с использованием встроенного шаблона пациентов, с нуля или путем импорта данных в Excel.</span><span class="sxs-lookup"><span data-stu-id="974f0-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="974f0-110">Дополнительные сведения об управлении приложением Lists в Организации можно найти в разделе [Управление приложением "списки"](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="974f0-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="974f0-111">Настройка или перенастройка сервера FHIR для работы с приложением Microsoft Teams пациентов требует понимания данных, к которым приложению требуется доступ.</span><span class="sxs-lookup"><span data-stu-id="974f0-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="974f0-112">Сервер FHIR должен поддерживать запросы POST, используя пакеты для указанных ниже ресурсов.</span><span class="sxs-lookup"><span data-stu-id="974f0-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="974f0-113">Подождите</span><span class="sxs-lookup"><span data-stu-id="974f0-113">Patient</span></span>](#patient)
- [<span data-ttu-id="974f0-114">Наблюдение</span><span class="sxs-lookup"><span data-stu-id="974f0-114">Observation</span></span>](#observation)
- [<span data-ttu-id="974f0-115">Условие</span><span class="sxs-lookup"><span data-stu-id="974f0-115">Condition</span></span>](#condition)
- [<span data-ttu-id="974f0-116">Происходит</span><span class="sxs-lookup"><span data-stu-id="974f0-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="974f0-117">Недопустимый Allergy</span><span class="sxs-lookup"><span data-stu-id="974f0-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="974f0-118">Приложения</span><span class="sxs-lookup"><span data-stu-id="974f0-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="974f0-119">Лечения заказ</span><span class="sxs-lookup"><span data-stu-id="974f0-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="974f0-120">Расположение</span><span class="sxs-lookup"><span data-stu-id="974f0-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="974f0-121">Ресурс пациент является единственным обязательным ресурсом (без которого приложение не будет загружаться вообще).</span><span class="sxs-lookup"><span data-stu-id="974f0-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="974f0-122">Тем не менее, рекомендуется, чтобы партнеры реализовали поддержку всех вышеупомянутых ресурсов для спецификаций, указанных ниже, для наилучшего взаимодействия с пользователем в приложении Microsoft Teams пациентов.</span><span class="sxs-lookup"><span data-stu-id="974f0-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="974f0-123">Запросы из приложения Microsoft Teams пациентов для нескольких ресурсов. отправляет набор (пакет) запросов на URL-адрес сервера FHIR.</span><span class="sxs-lookup"><span data-stu-id="974f0-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="974f0-124">Сервер обрабатывает каждый запрос и возвращает набор ресурсов, соответствующих каждому запросу.</span><span class="sxs-lookup"><span data-stu-id="974f0-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="974f0-125">Дополнительные сведения и примеры можно найти в разделе [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="974f0-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="974f0-126">Все перечисленные ниже ресурсы FHIR должны быть доступны по прямой ссылке на ресурс.</span><span class="sxs-lookup"><span data-stu-id="974f0-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="974f0-127">Минимальный набор полей, необходимый для установки соответствия</span><span class="sxs-lookup"><span data-stu-id="974f0-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="974f0-128">Сервер FHIR должен реализовать инструкцию соответствия, чтобы получить сводную информацию о ее возможностях factual.</span><span class="sxs-lookup"><span data-stu-id="974f0-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="974f0-129">Ниже перечислены параметры на сервере DSTU2 FHIR:</span><span class="sxs-lookup"><span data-stu-id="974f0-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="974f0-130">ДЕРЖИВАЕТ</span><span class="sxs-lookup"><span data-stu-id="974f0-130">REST</span></span>
   1. <span data-ttu-id="974f0-131">Режиме</span><span class="sxs-lookup"><span data-stu-id="974f0-131">Mode</span></span>
   2. <span data-ttu-id="974f0-132">Действует</span><span class="sxs-lookup"><span data-stu-id="974f0-132">Interaction</span></span>
   3. <span data-ttu-id="974f0-133">Ресурс: тип</span><span class="sxs-lookup"><span data-stu-id="974f0-133">Resource: Type</span></span>
   4. <span data-ttu-id="974f0-134">Безопасность: [расширение URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="974f0-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="974f0-135">FhirVersion (для нашего кода требуется, чтобы узнать, в какую версию следует поворачивать, так как мы поддерживаем несколько версий.)</span><span class="sxs-lookup"><span data-stu-id="974f0-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="974f0-136">[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="974f0-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="974f0-137">Подождите</span><span class="sxs-lookup"><span data-stu-id="974f0-137">Patient</span></span>

<span data-ttu-id="974f0-138">Это минимальные обязательные поля, которые являются подмножеством полей [профиля пациента Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :</span><span class="sxs-lookup"><span data-stu-id="974f0-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="974f0-139">Family (имя)</span><span class="sxs-lookup"><span data-stu-id="974f0-139">Name.Family</span></span>
2. <span data-ttu-id="974f0-140">Name (имя). задано</span><span class="sxs-lookup"><span data-stu-id="974f0-140">Name.Given</span></span>
3. <span data-ttu-id="974f0-141">Полу</span><span class="sxs-lookup"><span data-stu-id="974f0-141">Gender</span></span>
4. <span data-ttu-id="974f0-142">Рождения</span><span class="sxs-lookup"><span data-stu-id="974f0-142">BirthDate</span></span>
5. <span data-ttu-id="974f0-143">MRN (идентификатор)</span><span class="sxs-lookup"><span data-stu-id="974f0-143">MRN (Identifier)</span></span>

<span data-ttu-id="974f0-144">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также считывает следующие поля:</span><span class="sxs-lookup"><span data-stu-id="974f0-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="974f0-145">Name. use</span><span class="sxs-lookup"><span data-stu-id="974f0-145">Name.Use</span></span>
2. <span data-ttu-id="974f0-146">Name. prefix</span><span class="sxs-lookup"><span data-stu-id="974f0-146">Name.Prefix</span></span>
3. <span data-ttu-id="974f0-147">CareProvider (эта ссылка на ресурс пациент должна содержать отображаемые поля, показанные в приведенном ниже примере).</span><span class="sxs-lookup"><span data-stu-id="974f0-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="974f0-148">Запрос: получение <fhir-Server>/Patient/<пациент-ID></span><span class="sxs-lookup"><span data-stu-id="974f0-148">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="974f0-149">Ответ: {"resourceType": "Patient", "идентификатор": "<пациент-ID>";.</span><span class="sxs-lookup"><span data-stu-id="974f0-149">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="974f0-150">.</span><span class="sxs-lookup"><span data-stu-id="974f0-150">.</span></span>
      <span data-ttu-id="974f0-151">.</span><span class="sxs-lookup"><span data-stu-id="974f0-151">.</span></span>
      <span data-ttu-id="974f0-152">"имя": [{"use": "официальный", "префикс": ["MR"], "Family": ["Hugh"] "," ". [" Chau "]}]," идентификатор ": [{" использование ":" официальный "," тип ": {" программирование ": [{" System ":" "; https://hl7.org/fhir/v2/0203 " код ":" MR "}]};" значение ":" м ";" careProvider ": [{" Display ":" Джейн Петров "}],} 1234567 1957-06-05</span><span class="sxs-lookup"><span data-stu-id="974f0-152">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="974f0-153">Поиск ресурсов использует метод POST по адресу/Patient/_search и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="974f0-153">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="974f0-154">номер</span><span class="sxs-lookup"><span data-stu-id="974f0-154">id</span></span>
2. <span data-ttu-id="974f0-155">Семья: Contains = (ищет все пациентов, чье имя семейства оно содержат.)</span><span class="sxs-lookup"><span data-stu-id="974f0-155">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="974f0-156">указанный =\<substring></span><span class="sxs-lookup"><span data-stu-id="974f0-156">given=\<substring></span></span>
4. <span data-ttu-id="974f0-157">Name =\<substring></span><span class="sxs-lookup"><span data-stu-id="974f0-157">name=\<substring></span></span>
5. <span data-ttu-id="974f0-158">Дата рождения = (точное совпадение)</span><span class="sxs-lookup"><span data-stu-id="974f0-158">birthdate=(exact match)</span></span>
6. <span data-ttu-id="974f0-159">\_Count (максимальное количество возвращаемых результатов)</span><span class="sxs-lookup"><span data-stu-id="974f0-159">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="974f0-160">Ответ должен содержать общее количество записей, возвращенных в результате поиска, и \_ количество будет использоваться PatientsApp для ограничения количества возвращенных записей.</span><span class="sxs-lookup"><span data-stu-id="974f0-160">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="974f0-161">Идентификатор =\<mrn></span><span class="sxs-lookup"><span data-stu-id="974f0-161">identifier=\<mrn></span></span>

<span data-ttu-id="974f0-162">Цель — найти и отфильтровать пациента в пациент, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="974f0-162">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="974f0-163">ID: это идентификатор ресурса, который содержит каждый ресурс в FHIR.</span><span class="sxs-lookup"><span data-stu-id="974f0-163">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="974f0-164">MRN: фактический идентификатор пациента, который будет знать Clinical сотрудника.</span><span class="sxs-lookup"><span data-stu-id="974f0-164">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="974f0-165">Мы понимаем, что этот MRN основывается на типе идентификатора в ресурсе идентификатора в FHIR</span><span class="sxs-lookup"><span data-stu-id="974f0-165">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="974f0-166">Имя</span><span class="sxs-lookup"><span data-stu-id="974f0-166">Name</span></span>
- <span data-ttu-id="974f0-167">Рождения</span><span class="sxs-lookup"><span data-stu-id="974f0-167">Birthdate</span></span>

<span data-ttu-id="974f0-168">Ниже приведен пример этого звонка.</span><span class="sxs-lookup"><span data-stu-id="974f0-168">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="974f0-169">Запрос: POST <fhir-Server>/Patient/_search запроса: с указанным = Hugh&Family = Chau</span><span class="sxs-lookup"><span data-stu-id="974f0-169">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="974f0-170">Response: {"resourceType": "пакет", "идентификатор": "<-ID пакета>".</span><span class="sxs-lookup"><span data-stu-id="974f0-170">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="974f0-171">.</span><span class="sxs-lookup"><span data-stu-id="974f0-171">.</span></span>
      <span data-ttu-id="974f0-172">.</span><span class="sxs-lookup"><span data-stu-id="974f0-172">.</span></span>
      <span data-ttu-id="974f0-173">"Entry": [{"ресурс": {"resourceType": "пациент"; "идентификатор": "<пациент-ID>", "имя": [{"текст": "Hugh Chau", "семья": ["Chau"], ""--"," Дата ":" м ":"----------"1957-06-05</span><span class="sxs-lookup"><span data-stu-id="974f0-173">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="974f0-174">[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="974f0-174">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="974f0-175">Наблюдение</span><span class="sxs-lookup"><span data-stu-id="974f0-175">Observation</span></span>

<span data-ttu-id="974f0-176">Это минимальные обязательные поля, которые являются подмножеством профиля Argonaut важную подпись:</span><span class="sxs-lookup"><span data-stu-id="974f0-176">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="974f0-177">Эффективная (Дата и время)</span><span class="sxs-lookup"><span data-stu-id="974f0-177">Effective (date time or period)</span></span>
 2. <span data-ttu-id="974f0-178">Код. кодирование. Code</span><span class="sxs-lookup"><span data-stu-id="974f0-178">Code.Coding.Code</span></span>
 3. <span data-ttu-id="974f0-179">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="974f0-179">ValueQuantity.Value</span></span>

<span data-ttu-id="974f0-180">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также считывает следующие поля:</span><span class="sxs-lookup"><span data-stu-id="974f0-180">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="974f0-181">Код. программирование. Display</span><span class="sxs-lookup"><span data-stu-id="974f0-181">Code.Coding.Display</span></span>
 2. <span data-ttu-id="974f0-182">ValueQuantity. ед.</span><span class="sxs-lookup"><span data-stu-id="974f0-182">ValueQuantity.Unit</span></span>

<span data-ttu-id="974f0-183">При использовании наблюдения за компонентами одна и та же логика применяется для наблюдения за каждым компонентом.</span><span class="sxs-lookup"><span data-stu-id="974f0-183">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="974f0-184">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="974f0-184">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="974f0-185">пациент =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="974f0-185">patient=\<patient id\></span></span>
2. <span data-ttu-id="974f0-186">сортировка: DESC =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="974f0-186">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="974f0-187">Цель состоит в том, чтобы получить последние важные знаки для пациента, [VitalSigns. DSTU. saz] (наблюдение?).</span><span class="sxs-lookup"><span data-stu-id="974f0-187">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="974f0-188">Запрос: GET <fhir-Server>/Observation? пациент =<пациент-ID>&_sort:d ESC = Дата&Category = важные-признаки</span><span class="sxs-lookup"><span data-stu-id="974f0-188">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="974f0-189">Response: {"resourceType": "пакет", "идентификатор": <"пакет-ID>", "введите": ",", "," Итого ": 20," Entry ": [{" ресурс ": {" resourceType ":" наблюдение "," идентификатор ":" <ресурс-идентификатор> ";" Категория ": {" программирование ": [{code": "важные-знаки"}],}, "код": {"программирование": [{"System": " http://loinc.org "; "код": "39156-5", "Display": "BMI"}],}, "effectiveDateTime": "2009-12-01"; "valueQuantity": {"значение": 34,4; "единица": "кг/m2", "система": " http://unitsofmeasure.org кг/m2"}},},.</span><span class="sxs-lookup"><span data-stu-id="974f0-189">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="974f0-190">.</span><span class="sxs-lookup"><span data-stu-id="974f0-190">.</span></span>
        <span data-ttu-id="974f0-191">.</span><span class="sxs-lookup"><span data-stu-id="974f0-191">.</span></span>
      <span data-ttu-id="974f0-192">] }</span><span class="sxs-lookup"><span data-stu-id="974f0-192">] }</span></span>

* * *

<span data-ttu-id="974f0-193">[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="974f0-193">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="974f0-194">Условие</span><span class="sxs-lookup"><span data-stu-id="974f0-194">Condition</span></span>

<span data-ttu-id="974f0-195">Это минимальные обязательные поля, которые являются подмножеством [профиля условия Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="974f0-195">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="974f0-196">Код. кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="974f0-196">Code.Coding[0].Display</span></span>

<span data-ttu-id="974f0-197">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="974f0-197">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="974f0-198">Дата записи</span><span class="sxs-lookup"><span data-stu-id="974f0-198">Date Recorded</span></span>
2. <span data-ttu-id="974f0-199">Уровню серьезности</span><span class="sxs-lookup"><span data-stu-id="974f0-199">Severity</span></span>

<span data-ttu-id="974f0-200">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="974f0-200">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="974f0-201">пациент =\<patient id></span><span class="sxs-lookup"><span data-stu-id="974f0-201">patient=\<patient id></span></span>
2. <span data-ttu-id="974f0-202">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="974f0-202">_count=\<max results></span></span>

<span data-ttu-id="974f0-203">Ниже приведен пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="974f0-203">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="974f0-204">Запрос: GET <fhir-Server>/Condition? пациент =<пациент-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="974f0-204">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="974f0-205">Response: {"resourceType": "пакет", "идентификатор <": "набор-ID>", "тип": "набор поиска", "Итого", "элемент": [{"ресурс": {"имя ресурса": "условие", "идентификатор": "<Resource-id>", "код": {"программирование": [{"System": " http://snomed.info/sct ", "код": "386033004", "Display": "Neuropathy (Nerve)"}]}, "dateRecorded": "2018-09-17", "сервер": {"программирование": [{"System": " http://snomed.info/sct "; "код": "24484000"; "вывод": "серьезный"}]}}}]}</span><span class="sxs-lookup"><span data-stu-id="974f0-205">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="974f0-206">[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="974f0-206">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="974f0-207">Происходит</span><span class="sxs-lookup"><span data-stu-id="974f0-207">Encounter</span></span>

<span data-ttu-id="974f0-208">Это минимальные обязательные поля, которые являются подмножеством подмножества для основного профиля в США, которое должно иметь следующие поля:</span><span class="sxs-lookup"><span data-stu-id="974f0-208">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

1. <span data-ttu-id="974f0-209">Состояни</span><span class="sxs-lookup"><span data-stu-id="974f0-209">Status</span></span>
2. <span data-ttu-id="974f0-210">Введите [0]. Кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="974f0-210">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="974f0-211">Кроме того, ниже перечислены поля, которые можно получить из основного приложения US "требуется поддержка".</span><span class="sxs-lookup"><span data-stu-id="974f0-211">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

1. <span data-ttu-id="974f0-212">Period. Start</span><span class="sxs-lookup"><span data-stu-id="974f0-212">Period.Start</span></span>
2. <span data-ttu-id="974f0-213">Расположение [0]. Расположение. Display</span><span class="sxs-lookup"><span data-stu-id="974f0-213">Location[0].Location.Display</span></span>

<span data-ttu-id="974f0-214">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="974f0-214">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="974f0-215">пациент =\<patient id></span><span class="sxs-lookup"><span data-stu-id="974f0-215">patient=\<patient id></span></span>
2. <span data-ttu-id="974f0-216">_sort: DESC =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="974f0-216">_sort:desc=\<field ex. date></span></span>
3. <span data-ttu-id="974f0-217">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="974f0-217">_count=\<max results></span></span>

<span data-ttu-id="974f0-218">Цель — получить Последнее известное расположение пациента.</span><span class="sxs-lookup"><span data-stu-id="974f0-218">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="974f0-219">Каждый из этих обнаружений ссылается на ресурс расположения.</span><span class="sxs-lookup"><span data-stu-id="974f0-219">Each encounter references a location resource.</span></span> <span data-ttu-id="974f0-220">Ссылка также должна включать поле отображения местоположения.</span><span class="sxs-lookup"><span data-stu-id="974f0-220">The reference shall also include the location's display field.</span></span> <span data-ttu-id="974f0-221">Ниже приведен пример этого звонка.</span><span class="sxs-lookup"><span data-stu-id="974f0-221">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="974f0-222">Запрос: GET <fhir-Server>/Encounter? пациент =<пациент-ID>&_sort:d ESC = Дата&_count = 1</span><span class="sxs-lookup"><span data-stu-id="974f0-222">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="974f0-223">Ответ: {"resourceType": "комплект", "тип": "набор результатов поиска", "всего": 1, "элемент": [{"ресурс": {"ИД": "Поиск", "идентификатор"-"<ресурсов>"; "идентификатор": [{"use": "официальный", "значение": " <id> состояние": "поступило"; "тип": [{"код": [{"Display": "Встреча"}],}], "пациент": {"ссылка": "пациент/<пациент-ID"> "};" период ": {" начало ":" 09/17/2018 1:00:00 PM "}," расположение ": [{" расположение ": {" Display ":" курс-корпоративный "},}]}}]}</span><span class="sxs-lookup"><span data-stu-id="974f0-223">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="974f0-224">[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="974f0-224">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="974f0-225">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="974f0-225">AllergyIntolerance</span></span>

<span data-ttu-id="974f0-226">Это минимальные обязательные поля, которые являются подмножеством профиля Argonaut AllergyIntolerance:</span><span class="sxs-lookup"><span data-stu-id="974f0-226">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="974f0-227">Code. Text</span><span class="sxs-lookup"><span data-stu-id="974f0-227">Code.Text</span></span>
2. <span data-ttu-id="974f0-228">Код. кодирование [0]. Показан</span><span class="sxs-lookup"><span data-stu-id="974f0-228">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="974f0-229">Состояни</span><span class="sxs-lookup"><span data-stu-id="974f0-229">Status</span></span>

<span data-ttu-id="974f0-230">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также считывает следующие поля:</span><span class="sxs-lookup"><span data-stu-id="974f0-230">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="974f0-231">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="974f0-231">RecordedDate</span></span>
2. <span data-ttu-id="974f0-232">Примечание. текст</span><span class="sxs-lookup"><span data-stu-id="974f0-232">Note.Text</span></span>
3. <span data-ttu-id="974f0-233">Реакция [..]. Вещество. текст</span><span class="sxs-lookup"><span data-stu-id="974f0-233">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="974f0-234">Реакция [..]. Манифест [..]. Текстовые</span><span class="sxs-lookup"><span data-stu-id="974f0-234">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="974f0-235">Text. Div</span><span class="sxs-lookup"><span data-stu-id="974f0-235">Text.Div</span></span>

<span data-ttu-id="974f0-236">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="974f0-236">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="974f0-237">Пациент =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="974f0-237">Patient =  \<patient id></span></span>

<span data-ttu-id="974f0-238">Ниже приведен пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="974f0-238">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="974f0-239">Запрос: GET <fhir-Server>/AllergyIntolerance? пациент =<пациент-ID></span><span class="sxs-lookup"><span data-stu-id="974f0-239">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="974f0-240">Response: {"resourceType": "набор", "идентификатор <": "пакет-ID>", "тип": "набор поиска", "всего", "элемент": [{"ресурс": {"resourceType": "AllergyIntolerance", "идентификатор": "<Resource-id>", "recordedDate": "2018-09-17T07:00:00.000 Z", "веществ": {"текст": "Cashew" "}", "состояние": "подтверждено", "реакция": [{"вещество". ": {" текст ":" Cashew Гайк allergenic извлечь введенный продукт "}," проявление ": [{" текст ":" реакция на Anaphylactic "}]}</span><span class="sxs-lookup"><span data-stu-id="974f0-240">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="974f0-241">[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="974f0-241">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="974f0-242">Лечения заказ</span><span class="sxs-lookup"><span data-stu-id="974f0-242">Medication Order</span></span>

<span data-ttu-id="974f0-243">Это минимальные обязательные поля, которые являются подмножеством профиля Argonaut MedicationOrder:</span><span class="sxs-lookup"><span data-stu-id="974f0-243">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="974f0-244">DateWritten</span><span class="sxs-lookup"><span data-stu-id="974f0-244">DateWritten</span></span>
2. <span data-ttu-id="974f0-245">Предписанный. Display</span><span class="sxs-lookup"><span data-stu-id="974f0-245">Prescriber.Display</span></span>
3. <span data-ttu-id="974f0-246">Лечения. Display (если ссылка)</span><span class="sxs-lookup"><span data-stu-id="974f0-246">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="974f0-247">Лечения. Text (если понятие)</span><span class="sxs-lookup"><span data-stu-id="974f0-247">Medication.Text (if concept)</span></span>

<span data-ttu-id="974f0-248">В дополнение к полям Argonaut для удобства пользователей приложение пациентов также может прочитать следующие поля:</span><span class="sxs-lookup"><span data-stu-id="974f0-248">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="974f0-249">DateEnded</span><span class="sxs-lookup"><span data-stu-id="974f0-249">DateEnded</span></span>
2. <span data-ttu-id="974f0-250">DosageInstruction. Text</span><span class="sxs-lookup"><span data-stu-id="974f0-250">DosageInstruction.Text</span></span>
3. <span data-ttu-id="974f0-251">Text. Div</span><span class="sxs-lookup"><span data-stu-id="974f0-251">Text.Div</span></span>

<span data-ttu-id="974f0-252">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="974f0-252">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="974f0-253">пациент =\<patient id></span><span class="sxs-lookup"><span data-stu-id="974f0-253">patient=\<patient id></span></span>
2. <span data-ttu-id="974f0-254">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="974f0-254">_count=\<max results></span></span>

<span data-ttu-id="974f0-255">Ниже приведен пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="974f0-255">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="974f0-256">Запрос: GET <fhir-Server>/MedicationOrder? пациент =<пациент-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="974f0-256">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="974f0-257">Response: {"resourceType": "пакет", "идентификатор <": "набор-ID>", "тип": "набор поиска", "всего": 1, "запись": [{"ресурс": {"resourceType": "MedicationOrder", "идентификатор": "<ресурс-идентификатор>"; "dateWritten": "," medicationCodeableConcept ": {", ":" Lisinopril 20 mg устные Планшет "}," предназначается ": {" вывод ":" Джейн Петров "}," dosageInstruction ": [{" текст ":" 2018-09-17</span><span class="sxs-lookup"><span data-stu-id="974f0-257">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="974f0-258">[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="974f0-258">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="974f0-259">Приложения</span><span class="sxs-lookup"><span data-stu-id="974f0-259">Coverage</span></span>

<span data-ttu-id="974f0-260">Это минимальный обязательный набор полей, не охваченных профилями США или Argonaut:</span><span class="sxs-lookup"><span data-stu-id="974f0-260">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="974f0-261">Payor</span><span class="sxs-lookup"><span data-stu-id="974f0-261">Payor</span></span>

<span data-ttu-id="974f0-262">Поиск ресурсов использует метод GET и следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="974f0-262">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="974f0-263">пациент =\<patient id></span><span class="sxs-lookup"><span data-stu-id="974f0-263">patient=\<patient id></span></span>

<span data-ttu-id="974f0-264">Ниже приведен пример этого звонка:</span><span class="sxs-lookup"><span data-stu-id="974f0-264">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="974f0-265">Запрос: GET <fhir-Server>/Coverage? пациент =<пациент-ID></span><span class="sxs-lookup"><span data-stu-id="974f0-265">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="974f0-266">Ответ: {"resourceType": "пакет", "тип": "функция поиска", "Итого": 1, "запись": [{"ресурс": {"resourceType": "Coverage", "план": "без основного страхового обеспечения", "> <подписчик": "нет на месте", "на"> <</span><span class="sxs-lookup"><span data-stu-id="974f0-266">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="974f0-267">[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="974f0-267">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="974f0-268">Местоположение</span><span class="sxs-lookup"><span data-stu-id="974f0-268">Location</span></span>

<span data-ttu-id="974f0-269">Этот ресурс используется только в качестве ссылки на ресурс " [встреча](#encounter) ".</span><span class="sxs-lookup"><span data-stu-id="974f0-269">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="974f0-270">[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)Дополнительные сведения об этом множестве полей приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="974f0-270">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
