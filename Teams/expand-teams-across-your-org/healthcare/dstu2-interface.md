---
title: Интерфейс интеграции приложения "Пациенты" и EHR с DSTU2
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
description: Узнайте о спецификации интерфейса DSTU2 в Teams, в том числе о настройке или перенастройке сервера FHIR для работы с приложением "Пациенты" Microsoft Teams.
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
> С 30 октября 2020 г. приложение "Пациенты" [](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) было отменено и заменено приложением "Списки" в Teams. Данные приложения "Пациенты" хранятся в почтовом ящике группы Office 365, которая сохраняет данные команды. Все данные, связанные с приложением "Пациенты", сохраняются в этой группе, но к ним нельзя получить доступ через пользовательский интерфейс. Пользователи могут создавать списки повторно с помощью приложения ["Списки".](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)
>
>С помощью списков группы обслуживания в вашей организации здравоохранения могут создавать списки пациентов для различных сценариев: от округов и межпрофиларных собраний до общего наблюдения пациентов. Чтобы начать, ознакомьтесь с шаблоном "Пациенты" в списке. Дополнительные информацию об управлении приложением "Списки" в организации см. в приложении ["Управление списками".](../../manage-lists-app.md)

Для настройки или перенастройки сервера FHIR для работы с приложением "Пациенты" в Microsoft Teams необходимо понимать, какие данные необходимы приложению для доступа. Сервер FHIR должен поддерживать запросы POST с помощью пакетов для следующих ресурсов:

- [Пациент](#patient)
- [Наблюдение](#observation)
- [Условие](#condition)
- [Встреча](#encounter)
- [Заковывная скайп](#allergyintolerance)
- [Покрытие](#coverage)
- [Medication Order](#medication-order)
- [Расположение](#location)

> [!NOTE]
> Ресурс "Пациент" — это единственный обязательный ресурс (без которого приложение не будет загружаться). Однако партнеру рекомендуется реализовать поддержку для всех указанных выше ресурсов в соответствии с указанными ниже спецификациями, чтобы лучше всего работать с приложением "Пациенты" в Microsoft Teams.

Запросы из приложения "Пациенты" Microsoft Teams для более чем одного ресурса разоотмешяют пакет (BATCH) с запросами на URL-адрес сервера FHIR. Сервер обрабатывает каждый запрос и возвращает пакет ресурсов, которые соответствуют каждому запросу. Дополнительные сведения и примеры см. в [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .

Все следующие ресурсы FHIR должны быть доступны по прямой ссылке на них.

## <a name="conformance-minimum-required-field-set"></a>Набор полей соответствия

 Чтобы мы реализовали заявление о соответствии для FHIR Server, мы должны получить сводку о его возможностях. На FHIR-сервере DSTU2 мы ожидаем, что ниже заданы параметры:

 - REST

    - Режим
    - Взаимодействие
    - Ресурс: тип
    - Безопасность: [расширение для URIs OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
   
 - FhirVersion (В нашем коде это необходимо для того, чтобы понять, какую версию следует сархить, так как поддерживается несколько версий.)

Другие [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) сведения об этом наборе полей см. в этой области.

## <a name="patient"></a>Пациент

Они являются полями, которые являются подмножество полей профиля пациентов "Аргонаут": [](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)

 - Name.Family
 - Name.Given
 - Пол
 - BirthDate
 - MRN (Идентификатор)

Помимо полей "Аргонаут", приложение "Пациенты" также может читать следующие поля:

 - Name.Use
 - Name.Prefix
 - CareProvider (Ссылка на ресурс "Пациент" должна включать отображаемые поля, показанные в следующем примере).)

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

При поиске ресурсов метод POST используется для параметра /Patient/_search и следующих параметров:

 - id
 - family:contains=(ищет всех пациентов, имя которых содержит значение.)
 - given=\<substring>
 - name=\<substring>
 - birthdate=(exact match)
 - \_count (максимальное количество возвращаемых результатов) <br> Ответ должен содержать общее количество записей, возвращенных в результате поиска, и будет использоваться регистратором "Пациенты" для ограничения числа \_ возвращаемой записи.
 - идентификатор=\<mrn>

Цель состоит в том, чтобы иметь возможность поиска и фильтрации для пациента следующим образом:

- ИД: это ИД ресурса, который есть у каждого ресурса в FHIR.
- MRN: это фактический идентификатор пациента, который будет знать пациент. Мы понимаем, что эта MRN основана на типе идентификатора в идентификаторе ресурса в FHIR
- Имя
- Birthdate

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

## <a name="observation"></a>Наблюдение

Они являются полями, которые являются подмножество профиля важных знаков Argonaut:

 - Эффективные (дата или период)
 - Code.Coding.Code
 - ValueQuantity.Value

Помимо полей "Аргонаут", приложение "Пациенты" также может читать следующие поля:

 - Code.Coding.Display
 - ValueQuantity.Unit

При использовании наблюдений компонентов такая же логика применяется для каждого наблюдения компонентов.

При поиске ресурсов используются метод GET и следующие параметры:

 - patient=\<patient id\>
 - sort:desc=\<field ex. date\>

Цель — получить последние жизненно важные знаки для пациента [VitalSigns.DSTU.saz] (наблюдение?).

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

Это минимальные необходимые поля, которые являются подмножество профиля условия [Argonaut:](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)

1. Code.Coding[0]. Экран

Помимо полей "Аргонаут", приложение "Пациенты" также может читать следующие поля:

 - Дата записи
 - Серьезность

При поиске ресурсов используются метод GET и следующие параметры:

 - patient=\<patient id>
 - _count=\<max results>

См. пример этого звонка:

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

Это минимальные необходимые поля, которые являются подмножеством полей профиля Core Encounter в США:

 - Состояние
 - Введите[0]. Coding[0]. Экран

Кроме того, следующие поля из профилей US Core Encounter "необходимо поддерживать"

 - Period.Start
 - Location[0]. Location.Display

При поиске ресурсов используются метод GET и следующие параметры:

 - patient=\<patient id>
 - _sort:desc=\<field ex. date>
 - _count=\<max results>

Цель — получить последнее известное местоположение пациента. Каждое из этих встреч ссылается на ресурс расположения. В ссылку также должно быть включено отображаемого поля расположения. См. пример этого звонка.

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

## <a name="allergyintolerance"></a>Окномерации

Они являются полями, которые являются подмножество профиля Argonaut ВячестьIntolerance:

 - Code.Text
 - Code.Coding[0]. Экран
 - Состояние

Помимо полей "Аргонаут", приложение "Пациенты" также может читать следующие поля:

 - RecordedDate
 - Note.Text
 - Реакция[..]. Вааля.Текст
 - Реакция[..]. Заме же[..]. Текст
 - Text.Div

При поиске ресурсов используются метод GET и следующие параметры:

 - Patient =  \<patient id>

См. пример этого звонка:

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

## <a name="medication-order"></a>Medication Order

Они требуются для полей, которые являются частью профиля Argonaut Висячегов:

 - DateWritten
 - Висяк.Дисплей
 - Неявная.Дисплей (если ссылка)
 - Висяк.Текст (если концепция)

Помимо полей "Аргонаут", приложение "Пациенты" также может читать следующие поля:

 - DateEnded
 - Instruction.Text
 - Text.Div

При поиске ресурсов используются метод GET и следующие параметры:

 - patient=\<patient id>
 - _count=\<max results>

См. пример этого звонка:

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

Они требуются для полей, которые не охватываются профилями US Core или Argonaut.

 - Payor

При поиске ресурсов используются метод GET и следующие параметры:

 - patient=\<patient id>

См. пример этого звонка:

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

Этот ресурс используется только в качестве ссылки на ресурс [Encounter.](#encounter)

Другие [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) сведения об этом наборе полей см. в этой области.
