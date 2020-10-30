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
> Действительно 30 октября 2020 г. приложение пациентов было прекращено и заменено [приложением "списки](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) " в Teams. Данные приложения пациентов хранятся в почтовом ящике группы Office 365, которая является резервной командой. Все данные, связанные с приложением пациентов, сохраняются в этой группе, но их больше нельзя будет получить с помощью пользовательского интерфейса. Пользователи могут повторно создавать списки с помощью приложения " [списки](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)".
>
>Благодаря спискам, благодаря вашим командам в организации здравоохранения вы сможете создавать списки пациент для сценариев, начиная с округляющих и interdisciplinaryных собраний групп и заканчивая общим мониторингом пациента. Чтобы приступить к работе, изучите шаблон пациентов в списках. Дополнительные сведения об управлении приложением Lists в Организации можно найти в разделе [Управление приложением "списки"](../../manage-lists-app.md).

Настройка или перенастройка сервера FHIR для работы с приложением Microsoft Teams пациентов требует понимания данных, к которым приложению требуется доступ. Сервер FHIR должен поддерживать запросы POST, используя пакеты для указанных ниже ресурсов.

- [Подождите](#patient)
- [Наблюдение](#observation)
- [Условие](#condition)
- [Происходит](#encounter)
- [Недопустимый Allergy](#allergyintolerance)
- [Приложения](#coverage)
- [Оператор лечения](#medication-request) (заменяет MEDICATIONORDER в DSTU2 версии PatientsApp)
- Расположение (данные, необходимые для этого ресурса, могут быть включены в план)

> [!NOTE]
> Ресурс пациент является единственным обязательным ресурсом (без которого приложение не будет загружаться вообще); Тем не менее, рекомендуется, чтобы партнеры реализовали поддержку всех вышеупомянутых ресурсов для спецификаций, указанных ниже, для наилучшего взаимодействия с пользователем в приложении Microsoft Teams пациентов.

Запросы из приложения Microsoft Teams пациентов для более чем одного ресурса должны публиковать набор (пакет) запросов на URL-адрес сервера FHIR. Сервер должен обрабатывать каждый запрос и возвращать набор ресурсов, соответствующих каждому запросу. Дополнительные сведения и примеры можно найти в разделе [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .

## <a name="capability-statement"></a>Оператор возможностей

Ниже указаны минимальные обязательные поля.

 - ДЕРЖИВАЕТ

    - Режиме
    - Действует
    - Ресурс: тип
    - Безопасность: [расширение URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
    
 - FhirVersion (для нашего кода требуется, чтобы узнать, в какую версию следует поворачивать.)

[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)Дополнительные сведения об этом множестве полей приведены в разделе.

## <a name="patient"></a>Подождите

Ниже приведены минимальные обязательные поля, которые являются подмножеством полей профиля пациента Argonaut:

 - Name (имя). задано
 - Family (имя)
 - Полу
 - Рождения
 - MRN (идентификатор)

В дополнение к [полям Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)для удобства пользователей приложение пациентов также может прочитать следующие поля:

 - Name. use
 - Name. prefix
 - [GeneralPractitioner]-ссылка GeneralPractitioner должна включаться в ресурс пациент (только для отображения поля)

Поиск ресурсов использует метод POST по адресу/Patient/_search и следующие параметры:

 - номер
 - Family = (Поиск всех пациентов, чье имя семейства не содержало значение)
 - указанный =\<substring>
 - Дата рождения = (точное совпадение)
 - Gender = (значения являются одним из административных пола)
 - \_Count (максимальное количество возвращаемых результатов) <br> Ответ должен содержать общее количество записей, возвращенных в результате поиска, и \_ счетчик будет использоваться PatientsApp, чтобы ограничить количество возвращаемых записей.
 - Идентификатор =\<mrn>

Цель — найти и отфильтровать пациента в пациент, выполнив следующие действия:

- ID: это идентификатор ресурса, который содержит каждый ресурс в FHIR.
- MRN: фактический идентификатор пациента, который будет знать Clinical сотрудника. Мы понимаем, что этот MRN основывается на типе идентификатора в ресурсе идентификатора в FHIR.
- Имя
- Рождения

Посмотрите следующий пример звонка:

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

[https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html)Дополнительные сведения об этом множестве полей приведены в разделе.

## <a name="observation"></a>Наблюдение

Это минимальные обязательные поля, которые являются подмножеством [профиля Argonaut Vital-Signs](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).

 - Эффективная (Дата и время)
 - Код. кодирование. Code
 - ValueQuantity. Value

В дополнение к полям Argonaut для удобства пользователей приложение пациентов также может прочитать следующие поля:

 - Код. программирование. Display
 - ValueQuantity. ед.

Поиск ресурсов использует метод GET и следующие параметры:

 - пациент =\<patient id>
 - _sort =-Дата
 - Category (мы будем запрашивать "Category =", чтобы получить список важных знаков.

Ниже приведен пример звонка.

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

[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)Дополнительные сведения об этом множестве полей приведены в разделе.

## <a name="condition"></a>Условие

Ниже приведено минимально необходимое поле, которое является подмножеством [профиля условия Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).

 - Код. кодирование [0]. Показан

В дополнение к полям Argonaut для удобства пользователей приложение пациентов также может прочитать следующие поля:

 - AssertedDate
 - Уровню серьезности

Поиск ресурсов использует метод GET и следующие параметры:

 - пациент =\<patient id>
 - _count =\<max results>

Ниже приведен пример этого звонка:

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

[https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html)Дополнительные сведения об этом множестве полей приведены в разделе.

## <a name="encounter"></a>Происходит

Это минимальные обязательные поля, которые являются подмножеством подмножества [основного профиля](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) , которое должно иметь "поля".

 - Состояни
 - Введите [0]. Кодирование [0]. Показан

Кроме того, ниже перечислены поля, которые можно получить из основных полей "требуется поддержка" для профиля в США.

 - Period. Start
 - Расположение [0]. Расположение. Display

Поиск ресурсов использует метод GET и следующие параметры:

 - пациент =\<patient id>
 - _sort: DESC =\<field ex. date>
 - _count =\<max results>

Цель — получить Последнее известное расположение пациента. Каждый из этих обнаружений ссылается на ресурс расположения. Ссылка также должна включать поле отображения местоположения.

[https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html)Дополнительные сведения об этом множестве полей приведены в разделе.

## <a name="allergyintolerance"></a>AllergyIntolerance

Это минимальные обязательные поля, которые являются подмножеством профиля [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :

 - Code. Text
 - Код. кодирование [0]. Показан
 - ClinicalStatus/VerificationStatus (мы прочитали оба)

В дополнение к полям Argonaut для удобства пользователей приложение пациентов также может прочитать следующее поле:

 - AssertedDate
 - Примечание. текст
 - Реакция
    - Вещество (один элемент кодирования)
    - Манифест (один элемент кодирования)

Поиск ресурсов использует метод GET и следующие параметры:

 - Пациент =  \<patient id>

Посмотрите следующий пример звонка: 

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

[https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html)Дополнительные сведения об этом множестве полей приведены в разделе.

## <a name="medication-request"></a>Запрос лечения

Ниже указаны минимальные обязательные поля, которые являются подмножеством [профиля запроса "основной лечения" США](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html).

 - Лечения. Display (если ссылка)
 - Лечения. Text (если CodableConcept)
 - AuthoredOn
 - Запросивший. агент. Display

В дополнение к полям "основные" в США для удобства пользователей приложение пациентов также может прочитать следующие поля:

 - DosageInstruction[..]. Текстовые
 - Текстовые

Поиск ресурсов использует метод GET и следующие параметры:

 - пациент =\<patient id>
 - _count =\<max results>

[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)Дополнительные сведения об этом множестве полей приведены в разделе.

## <a name="coverage"></a>Приложения

Это минимальный обязательный набор полей, не охваченных профилями США или Argonaut:

 - Группировка, по крайней мере один элемент с
    - GroupDisplay
    - PlanDisplay
 - Срока
 - SubscriberId

Поиск ресурсов использует метод GET и следующие параметры:

 - Пациент = \<patient id>

[https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)Дополнительные сведения об этом множестве полей приведены в разделе.
