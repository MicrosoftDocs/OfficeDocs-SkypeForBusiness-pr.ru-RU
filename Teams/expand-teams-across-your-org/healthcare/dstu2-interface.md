---
title: Интерфейс DSTU2 интеграции приложения для пациентов и EHR
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
description: Узнайте о спецификации интерфейса DSTU2 в Teams, включая настройку или настройку FHIR-сервера для работы с приложением "Пациенты Microsoft Teams".
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 12833ea55977cf7e8d18ee5c10b1f17d898b27b3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803487"
---
# <a name="dstu2-interface-specification"></a>Характеристики интерфейса DSTU2

> [!NOTE]
> С 30 октября 2020 г. приложение "Пациенты" устарело и заменено приложением [Lists](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) в Teams. Данные приложения "Пациенты" хранятся в почтовом ящике группы Office 365, на которой основана команда. Все данные, связанные с приложением "Пациенты", сохраняются в этой группе, но больше недоступны в пользовательском интерфейсе. Пользователи могут повторно создать свои списки с помощью приложения [Lists](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>С помощью приложения Lists медицинские бригады вашей организации здравоохранения могут создавать списки пациентов для различных сценариев: от обходов и собраний междисциплинарных команд до общего наблюдения за пациентами. Ознакомьтесь с шаблоном "Пациенты" в приложении Lists, чтобы начать работу. Дополнительные сведения об управлении приложением Lists в организации см. в статье [Управление приложением Lists](../../manage-lists-app.md).

Для настройки или перенастройки FHIR-сервера для работы с приложением Microsoft Teams "Пациенты" требуется понимание данных, необходимых приложению для доступа. Сервер FHIR должен поддерживать запросы POST с использованием пакетов для следующих ресурсов:

- [Пациента](#patient)
- [Наблюдения](#observation)
- [Условие](#condition)
- [Встреча](#encounter)
- [Ветвная похоть](#allergyintolerance)
- [Покрытие](#coverage)
- [Заказ на прием приемов](#medication-order)
- [Расположение](#location)

> [!NOTE]
> Ресурс Patient — единственный обязательный ресурс (без которого приложение не будет загружаться). Однако партнеру рекомендуется реализовать поддержку для всех указанных выше ресурсов в соответствии с указанными ниже спецификациями, чтобы лучше работать с приложением Microsoft Teams пациентов.

Запросы из Microsoft Teams "Пациенты" для более чем одного ресурса выдают пакет запросов (BATCH) по URL-адресу сервера FHIR. Сервер обрабатывает каждый запрос и возвращает пакет ресурсов, которые соответствуют каждому запросу. Дополнительные сведения и примеры см. в [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .

Все следующие ресурсы FHIR должны быть доступны по прямой ссылке на них.

## <a name="conformance-minimum-required-field-set"></a>Набор полей соответствия

 FHIR Server должен реализовать заявление о соответствии, чтобы мы были фактическими сводными сведениями о его возможностях. Ниже параметров на FHIR-сервере DSTU2:

 - Остальные

    - Режим
    - Взаимодействия
    - Ресурс: введите
    - Безопасность: [расширение для URL-адресов OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
   
 - FhirVersion (код требует этого, чтобы понять, какую версию следует свертить, так как поддерживается несколько версий.)

Другие [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) сведения об этом наборе полей см. в этой области.

## <a name="patient"></a>Пациента

Это минимальные необходимые поля, которые являются частью полей профиля пациентов [Argonaut:](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)

 - Name.Family
 - Name.Given
 - Гендерного
 - Рождения
 - MRN (идентификатор)

Помимо полей "Аргонаут", приложение "Пациенты" также читает следующие поля:

 - Name.Use
 - Name.Prefix
 - CareProvider (Ссылка на ресурс Patient должна включать поля отображения, показанные в следующем примере.)

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

При поиске ресурсов используется метод POST в /Patient/_search и следующие параметры:

 - Id
 - family:contains=(ищет всех пациентов, имя семьи которых содержит значение.)
 - given=\<substring>
 - name=\<substring>
 - birthdate=(точное совпадение)
 - \_count (максимальное количество возвращаемых результатов) <br> Ответ должен содержать общее количество записей, возвращенных в результате поиска, и будет использоваться patientsApp для ограничения числа \_ возвращаемой записи.
 - identifier=\<mrn>

Цель состоит в том, чтобы иметь возможность поиска и фильтрации для пациента следующим образом:

- ИД. Это ИД ресурса, который есть у каждого ресурса в FHIR.
- MRN: это фактический идентификатор пациента, который бы узнали сотрудники медицинской службы. Мы понимаем, что это mrN основано на типе идентификатора внутри ресурса идентификатора в FHIR
- Имя
- Рождения

См. пример этого звонка.

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

Другие [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) сведения об этом наборе полей см. в этой области.

## <a name="observation"></a>Наблюдения

Это минимальные необходимые поля, которые являются частью профиля важных знаков Argonaut:

 - Эффект (дата или период)
 - Code.Coding.Code
 - ValueQuantity.Value

Помимо полей "Аргонаут", приложение "Пациенты" также читает следующие поля:

 - Code.Coding.Display
 - ValueQuantity.Unit

При использовании наблюдений компонентов для каждого наблюдения компонентов применяется та же логика.

При поиске ресурсов используются метод GET и следующие параметры:

 - patient=\<patient id\>
 - sort:desc=\<field ex. date\>

Цель — получить последние важные знаки для пациента [VitalSigns.DSTU.saz] (наблюдение?).

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

Другие [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) сведения об этом наборе полей см. в этой области.

## <a name="condition"></a>Условие

Это минимальные необходимые поля, которые являются частью профиля условий [Argonaut:](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)

1. Code.Coding[0]. Отображения

Помимо полей "Аргонаут", приложение "Пациенты" может прочитать следующие поля:

 - Дата записи
 - Тяжести

При поиске ресурсов используются метод GET и следующие параметры:

 - patient=\<patient id>
 - _count=\<max results>

См. пример следующего звонка:

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

Другие [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) сведения об этом наборе полей см. в этой области.

## <a name="encounter"></a>Встреча

Это минимальные необходимые поля, которые являются подмножество полей профиля Core Encounter в США:

 - Статус
 - Введите[0]. Код[0]. Отображения

Кроме того, следующие поля из профиля Core Encounter (США) должны поддерживаться.

 - Period.Start
 - Расположение[0]. Location.Display

При поиске ресурсов используются метод GET и следующие параметры:

 - patient=\<patient id>
 - _sort:desc=\<field ex. date>
 - _count=\<max results>

Цель — получить последнее известное местоположение пациента. Каждая встреча ссылается на ресурс расположения. Ссылка также должна включать отображаемого поля расположения. См. пример этого звонка.

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

Другие [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) сведения об этом наборе полей см. в этой области.

## <a name="allergyintolerance"></a>Омоластивная возможность

Это минимальные необходимые поля, которые являются частью профиля Argonaut ТемныеИннолерации:

 - Code.Text
 - Code.Coding[0]. Отображения
 - Статус

Помимо полей "Аргонаут", приложение "Пациенты" также читает следующие поля:

 - RecordedDate
 - Note.Text
 - Реакция[..]. Заме желтая.текстовая
 - Реакция[..]. Заявка[..]. Текст
 - Text.Div

При поиске ресурсов используются метод ПОЛУЧИТЬ и следующие параметры:

 - Patient =  \<patient id>

См. пример следующего звонка:

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

Другие [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) сведения об этом наборе полей см. в этой области.

## <a name="medication-order"></a>Заказ на прием приемов

Это минимальные необходимые поля, которые являются частью профиля Argonaut MedicationOrder:

 - DateWritten
 - Кливер.Отобразить
 - "Прием".Дисплей (если ссылка)
 - Medication.Text (если понятие)

Помимо полей "Аргонаут", приложение "Пациенты" может прочитать следующие поля:

 - DateEnded
 - ДелинейцияУстановка.Текст
 - Text.Div

При поиске ресурсов используются метод ПОЛУЧИТЬ и следующие параметры:

 - patient=\<patient id>
 - _count=\<max results>

См. пример следующего звонка:

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

Другие [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) сведения об этом наборе полей см. в этой области.

## <a name="coverage"></a>Покрытие

Это минимальные необходимые поля, не охватываемых профилями US Core или Argonaut:

 - Payor

При поиске ресурсов используются метод ПОЛУЧИТЬ и следующие параметры:

 - patient=\<patient id>

См. пример следующего звонка:

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
    
Другие [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) сведения об этом наборе полей см. в этой области.

## <a name="location"></a>Местоположение

Этот ресурс используется только в качестве ссылки на [ресурс Encounter.](#encounter)

Другие [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) сведения об этом наборе полей см. в этой области.
