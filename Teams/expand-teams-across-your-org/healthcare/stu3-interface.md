---
title: Интерфейс STU3 интеграции приложения "Пациенты" и EHR
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
description: Узнайте, как интегрировать электронные медицинские записи в приложение "Пациенты" Microsoft Teams и спецификацию интерфейса STU3.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e20619badb2509d0a90f396563a98796e718e2f
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803497"
---
# <a name="stu3-interface-specification"></a>Характеристики интерфейса STU3

> [!NOTE]
> С 30 октября 2020 г. приложение "Пациенты" [](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) было отменено и заменено приложением "Списки" в Teams. Данные приложения "Пациенты" хранятся в почтовом ящике группы Office 365, которая сохраняет данные команды. Все данные, связанные с приложением "Пациенты", сохраняются в этой группе, но к ним нельзя получить доступ через пользовательский интерфейс. Пользователи могут создавать списки повторно с помощью приложения ["Списки".](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)
>
>С помощью списков группы обслуживания в вашей организации здравоохранения могут создавать списки пациентов для различных сценариев: от округов и межпрофиларных собраний до общего наблюдения пациентов. Чтобы начать, ознакомьтесь с шаблоном "Пациенты" в списке. Дополнительные информацию об управлении приложением "Списки" в организации см. в приложении ["Управление списками".](../../manage-lists-app.md)

Для настройки или перенастройки сервера FHIR для работы с приложением "Пациенты" в Microsoft Teams необходимо понимать, какие данные необходимы приложению для доступа. Сервер FHIR должен поддерживать запросы POST с помощью пакетов для следующих ресурсов:

- [Пациент](#patient)
- [Наблюдение](#observation)
- [Условие](#condition)
- [Встреча](#encounter)
- [Заковырова Скайп](#allergyintolerance)
- [Покрытие](#coverage)
- [Выписка](#medication-request) по совместим (в DSTU2-версии patientsApp)
- Расположение (сведения, необходимые для этого ресурса, могут быть включены в encounter)

> [!NOTE]
> Ресурс "Пациент" — это единственный обязательный ресурс (без которого приложение не будет загружаться); Однако партнеру рекомендуется реализовать поддержку для всех указанных выше ресурсов в соответствии с указанными ниже спецификациями, чтобы лучше всего работать с приложением "Пациенты" в Microsoft Teams.

Запросы из приложения "Пациенты" Microsoft Teams для более чем одного ресурса должны опубликовать пакет запросов (BATCH) по URL-адресу сервера FHIR. Сервер должен обработать каждый запрос и вернуть пакет ресурсов, которые соответствуют каждому запросу. Дополнительные сведения и примеры см. в [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .

## <a name="capability-statement"></a>Заявление о возможности

Это поля, которые требуются для минимального размера:

 - REST

    - Режим
    - Взаимодействие
    - Ресурс: тип
    - Безопасность: [расширение для URIs OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
    
 - FhirVersion (этот код необходим для того, чтобы понять, какую версию следует сархить.)

Другие [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) сведения об этом наборе полей см. в этой области.

## <a name="patient"></a>Пациент

Вот поля, которые требуются в подмножество полей профиля пациентов "Аргонаут":

 - Name.Given
 - Name.Family
 - Пол
 - BirthDate
 - MRN (Идентификатор)

Помимо полей ["Аргонаут",](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)приложение "Пациенты" также может читать следующие поля:

 - Name.Use
 - Name.Prefix
 - [GeneralPractitioner] — ссылка на GeneralPractitioner должна быть включена в ресурс "Пациент" (только для отображения поля).

При поиске ресурсов метод POST используется для параметра /Patient/_search и следующих параметров:

 - id
 - family=(ищет всех пациентов, имя которых содержит значение)
 - given=\<substring>
 - birthdate=(exact match)
 - gender=(значения в административных полах)
 - \_count (максимальное количество возвращаемых результатов) <br> Ответ должен содержать общее количество записей, возвращенных в результате поиска, и количество будет использоваться регистратором "Пациенты" для ограничения числа \_ возвращаемой записи.
 - идентификатор=\<mrn>

Цель состоит в том, чтобы иметь возможность поиска и фильтрации для пациента следующим образом:

- ИД: это ИД ресурса, который есть у каждого ресурса в FHIR.
- MRN: это фактический идентификатор пациента, который будет знать пациент. Мы понимаем, что эта MRN основана на типе идентификатора внутри ресурса идентификатора в FHIR.
- Имя
- Birthdate

См. пример звонка:

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=ruth&family=black

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "meta": {
    "lastUpdated": "2019-01-14T23:44:45.052+00:00"
  },
  "type": "searchset",
  "total": 1,
  "link": [
    {
      "relation": "self",
      "url": <fhir-server>/Patient/_search"
    }
  ],
  "entry": [
    {
      "fullUrl": <fhir-server>/Patient/<patient-id>",
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "meta": {
          "versionId": "1",
          "lastUpdated": "2017-10-18T18:32:37.000+00:00"
        },
        "text": {
          "status": "generated",
          "div": "<div>\n        <p>Ruth Black</p>\n      </div>"
        },
        "identifier": [
          {
            "use": "usual",
            "type": {
              "coding": [
                {
                  "system": "https://hl7.org/fhir/v2/0203",
                  "code": "MR",
                  "display": "Medical record number",
                  "userSelected": false
                }
              ],
              "text": "Medical record number"
            },
            "system": "http://hospital.smarthealthit.org",
            "value": "1234567"
          }
        ],
        "active": true,
        "name": [
          {
            "use": "official",
            "family": "Black",
            "given": [
              "Ruth",
              "C."
            ]
          }
        ],
        "telecom": [
          {
            "system": "phone",
            "value": "800-599-2739",
            "use": "home"
          },
          {
            "system": "phone",
            "value": "800-808-7785",
            "use": "mobile"
          },
          {
            "system": "email",
            "value": "ruth.black@example.com"
          }
        ],
        "gender": "female",
        "birthDate": "1951-08-23",
        "address": [
          {
            "use": "home",
            "line": [
              "26 South RdApt 22"
            ],
            "city": "Sapulpa",
            "state": "OK",
            "postalCode": "74066",
            "country": "USA"
          }
        ]
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

```
Request:
GET <fhir-server>/Patient/<patient-id>

Response:
{
  "resourceType": "Patient",
  "id": "<patient-id>",
  "identifier": [
    {
      "use": "usual",
      "type": {
        "coding": [
          {
            "system": "https://hl7.org/fhir/v2/0203",
            "code": "MR",
          }
        ],
        "text": "Medical record number"
      },
      "value": "1234567"
    }
  ],
  "name": [
    {
      "use": "official",
      "family": "Adams",
      "given": [ "Daniel", "X." ]
    }
  ],
  "gender": "male",
  "birthDate": "1925-12-23",
}
```

Другие [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) сведения об этом наборе полей см. в этой области.

## <a name="observation"></a>Наблюдение

Они являются полями, которые являются подмножество профиля [Argonaut Vital-Signs.](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)

 - Эффективные (дата или период)
 - Code.Coding.Code
 - ValueQuantity.Value

Помимо полей "Аргонаут", приложение "Пациенты" также может читать следующие поля:

 - Code.Coding.Display
 - ValueQuantity.Unit

При поиске ресурсов используются метод GET и следующие параметры:

 - patient=\<patient id>
 - _sort=-дата
 - (мы запросим "category=vital-signs"), чтобы получить список важных знаков.

Обратитесь к примеру звонка:

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs

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
        "category": [
          {
            "coding": [
              {
                "system": "https://hl7.org/fhir/observation-category",
                "code": "vital-signs"
              }
            ],
          }
        ],
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "8867-4",
              "display": "heart_rate"
            }
          ]
        },
        "effectiveDateTime": "2009-04-08T00:00:00-06:00",
        "valueQuantity": {
          "value": 72.0,
          "unit": "{beats}/min",
          "system": "http://unitsofmeasure.org",
        }
      }
    },
    .
    .
    .
  ]
}
```

Другие [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) сведения об этом наборе полей см. в этой области.

## <a name="condition"></a>Условие

Вот минимально необходимые поля, которые являются подмножество профиля условия [Argonaut.](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)

 - Code.Coding[0]. Экран

Помимо полей "Аргонаут", приложение "Пациенты" также может читать следующие поля:

 - ВисячийДата
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
  "total": 2,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "185903001",
              "display": "Needs influenza immunization",
            }
          ]
        },
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        },
        "assertedDate": "2018-04-04"
      }
    },
    .
    .
    .
  ]
}
```

Другие [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) сведения об этом наборе полей см. в этой области.

## <a name="encounter"></a>Встреча

Это минимальные необходимые поля, которые являются подмножеством полей профиля [Core Encounter](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) в США.

 - Состояние
 - Введите[0]. Coding[0]. Экран

Кроме того, следующие поля из профилей US Core Encounter "необходимо поддерживать":

 - Period.Start
 - Location[0]. Location.Display

При поиске ресурсов используются метод GET и следующие параметры:

 - patient=\<patient id>
 - _sort:desc=\<field ex. date>
 - _count=\<max results>

Цель — получить последнее известное местоположение пациента. Каждое из этих встреч ссылается на ресурс расположения. В ссылку также должно быть включено отображаемого поля расположения.

Другие [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) сведения об этом наборе полей см. в этой области.

## <a name="allergyintolerance"></a>Окномерации

Они являются полями, которые являются подмножество профиля [Argonaut ВячестьIntolerance:](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html)

 - Code.Text
 - Code.Coding[0]. Экран
 - Клиническийтаис/Проверка (мы читаем оба)

Помимо полей "Аргонаут", приложение "Пациенты" также может прочесть следующее поле:

 - ВисячийДата
 - Note.Text
 - Реакция
    - Ухмайл (один элемент кода)
    - Ветвь (один элемент кода)

При поиске ресурсов используются метод GET и следующие параметры:

 - Patient =  \<patient id>

См. пример звонка: 

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
        "clinicalStatus": "active",
        "verificationStatus": "confirmed",
        "code": {
          "coding": [
            {
              "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",
              "code": "N0000175503",
              "display": "sulfonamide antibacterial",
            }
          ],
          "text": "sulfonamide antibacterial"
        },
        "assertedDate": "2018-01-01T00:00:00-07:00",
        "reaction": [
          {
            "manifestation": [
              {
                "coding": [
                  {
                    "system": "http://snomed.info/sct",
                    "code": "271807003",
                    "display": "skin rash",
                  }
                ],
                "text": "skin rash"
              }
            ],
          }
        ]
      }
    }
  ]
}
```

Другие [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) сведения об этом наборе полей см. в этой области.

## <a name="medication-request"></a>Запрос на прием

Они являются полями, которые являются подмножество профиля основного запроса основного ядра [США:](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)

 - Ия.Дисплей (если ссылка)
 - Висячий.Текст (если CodableConcept)
 - AuthoredOn
 - Requester.Agent.Display

Кроме полей "Us Core", приложение "Пациенты" может читать следующие поля:

 - Instruction[..]. Текст
 - Текст

При поиске ресурсов используются метод GET и следующие параметры:

 - patient=\<patient id>
 - _count=\<max results>

Другие [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) сведения об этом наборе полей см. в этой области.

## <a name="coverage"></a>Покрытие

Они требуются для полей, которые не охватываются профилями US Core или Argonaut.

 - Группировка, по крайней мере один элемент с
    - GroupDisplay
    - PlanDisplay
 - Период
 - SubscriberId

При поиске ресурсов используются метод GET и следующие параметры:

 - Patient = \<patient id>

Другие [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) сведения об этом наборе полей см. в этой области.
