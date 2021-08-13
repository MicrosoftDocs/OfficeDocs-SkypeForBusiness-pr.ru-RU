---
title: Интерфейс STU3 для интеграции приложения patients и EHR
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
description: Узнайте, как интегрировать электронные медицинские записи в приложение Microsoft Teams Patients и спецификацию интерфейса STU3.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e51372f2c44bdd5bdeea8e4a7699d3f46881564e0c98f3049b95dcbd21eb66c2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344050"
---
# <a name="stu3-interface-specification"></a>Характеристики интерфейса STU3

> [!NOTE]
> С 30 октября 2020 г. приложение "Пациенты" устарело и заменено приложением [Lists](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) в Teams. Данные приложения "Пациенты" хранятся в почтовом ящике группы Office 365, на которой основана команда. Все данные, связанные с приложением "Пациенты", сохраняются в этой группе, но больше недоступны в пользовательском интерфейсе. Пользователи могут повторно создать свои списки с помощью приложения [Lists](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>С помощью приложения Lists медицинские бригады вашей организации здравоохранения могут создавать списки пациентов для различных сценариев: от обходов и собраний междисциплинарных команд до общего наблюдения за пациентами. Ознакомьтесь с шаблоном "Пациенты" в приложении Lists, чтобы начать работу. Дополнительные сведения об управлении приложением Lists в организации см. в статье [Управление приложением Lists](../../manage-lists-app.md).

Для настройки или перенастройки FHIR-сервера для работы с приложением "Пациенты Microsoft Teams "Пациенты" требуется понимание данных, необходимых приложению для доступа. Сервер FHIR должен поддерживать запросы POST с использованием пакетов для следующих ресурсов:

- [Пациента](#patient)
- [Наблюдения](#observation)
- [Условие](#condition)
- [Встреча](#encounter)
- [Ветвная хламя](#allergyintolerance)
- [Покрытие](#coverage)
- [Выписка о](#medication-request) приеме приеме (заменяет "Order" в DSTU2-версии PatientsApp)
- Расположение (сведения, необходимые для этого ресурса, могут быть включены в сведения о контакте)

> [!NOTE]
> Ресурс Patient — единственный обязательный ресурс (без которого приложение не будет загружаться); Однако партнеру рекомендуется реализовать поддержку для всех указанных выше ресурсов в соответствии с указанными ниже спецификациями, чтобы лучше работать с приложением Microsoft Teams пациентов.

Запросы из приложения Microsoft Teams Patients для более чем одного ресурса должны опубликовать пакет запросов (BATCH) в URL-адрес сервера FHIR. Сервер обрабатывает каждый запрос и возвращает пакет ресурсов, которые соответствуют каждому запросу. Дополнительные сведения и примеры см. в [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .

## <a name="capability-statement"></a>Заявление о возможности

Это минимальные необходимые поля:

 - Остальные

    - Режим
    - Взаимодействие
    - Ресурс: введите
    - Безопасность: [расширение для URL-адресов OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
    
 - FhirVersion (код требует этого, чтобы понять, в какую версию следует свертить.)

Другие [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) сведения об этом наборе полей см. в этой области.

## <a name="patient"></a>Пациента

Ниже 2010 г. ниже 2010 г.

 - Name.Given
 - Name.Family
 - Гендерного
 - Рождения
 - MRN (идентификатор)

Помимо полей ["Аргонаут",](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)приложение "Пациенты" также может прочитать следующие поля:

 - Name.Use
 - Name.Prefix
 - [GeneralPractitioner] — справочник GeneralPractitioner должен быть включен в ресурс Patient (только отображаемая ссылка)

При поиске ресурсов используется метод POST в пункте /Patient/_search и следующие параметры:

 - Id
 - family=(поиск всех пациентов, имя семьи которых содержит значение)
 - given=\<substring>
 - birthdate=(точное совпадение)
 - gender=(значения одного из административных полов)
 - \_count (максимальное количество возвращаемых результатов) <br> Ответ должен содержать общее количество записей, возвращенных в результате поиска, и будет использоваться patientsApp для ограничения числа \_ возвращаемой записи.
 - identifier=\<mrn>

Цель состоит в том, чтобы иметь возможность поиска и фильтрации для пациента следующим образом:

- ИД. Это ИД ресурса, который есть у каждого ресурса в FHIR.
- MRN: это фактический идентификатор пациента, который бы узнали сотрудники медицинской службы. Мы понимаем, что это mrN основано на типе идентификатора внутри ресурса идентификатора в FHIR.
- Имя
- Рождения

См. следующий пример звонка:

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

## <a name="observation"></a>Наблюдения

Это минимальные необходимые поля, которые являются частью профиля [Argonaut Vital-Signs .](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)

 - Эффект (дата или период)
 - Code.Coding.Code
 - ValueQuantity.Value

Помимо полей "Аргонаут", приложение "Пациенты" может прочитать следующие поля:

 - Code.Coding.Display
 - ValueQuantity.Unit

При поиске ресурсов используются метод GET и следующие параметры:

 - patient=\<patient id>
 - _sort=дата
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

Вот минимально необходимые поля, которые являются частью профиля условий [Argonaut.](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)

 - Code.Coding[0]. Отображения

Помимо полей "Аргонаут", приложение "Пациенты" может прочитать следующие поля:

 - Твердаядата
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

Это минимальные необходимые поля, которые являются подмножество полей профиля [Core Encounter](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) в США.

 - Статус
 - Введите[0]. Код[0]. Отображения

Кроме того, поля "необходимо поддерживать" из профиля Core Encounter в США:

 - Period.Start
 - Расположение[0]. Location.Display

При поиске ресурсов используются метод GET и следующие параметры:

 - patient=\<patient id>
 - _sort:desc=\<field ex. date>
 - _count=\<max results>

Цель — получить последнее известное местоположение пациента. Каждая встреча ссылается на ресурс расположения. Ссылка также должна включать отображаемого поля расположения.

Другие [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) сведения об этом наборе полей см. в этой области.

## <a name="allergyintolerance"></a>Омоластивная возможность

Это минимальные необходимые поля, которые являются частью профиля [Argonaut ТемныеИннолерации:](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html)

 - Code.Text
 - Code.Coding[0]. Отображения
 - Кодификация и проверофикация (мы читаем и то, и другое)

Помимо полей "Аргонаут", приложение "Пациенты" может прочитать следующее поле:

 - Твердаядата
 - Note.Text
 - Реакции
    - Куапка (один элемент кодирования)
    - Куапка (один элемент кодирования)

При поиске ресурсов используются метод GET и следующие параметры:

 - Patient =  \<patient id>

См. следующий пример звонка: 

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

## <a name="medication-request"></a>Запрос на прием приемов

Это минимальные необходимые поля, которые являются частью профиля основного запроса на прием [щенок в США:](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)

 - "Прием".Дисплей (если ссылка)
 - Medication.Text (если CodableConcept)
 - AuthoredOn
 - Requester.Agent.Display

Помимо полей "Основные точки США" приложение "Пациенты" также может прочитать следующие поля:

 - ЕстрацияУстановка[..]. Текст
 - Текст

При поиске ресурсов используются метод GET и следующие параметры:

 - patient=\<patient id>
 - _count=\<max results>

Другие [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) сведения об этом наборе полей см. в этой области.

## <a name="coverage"></a>Покрытие

Это минимальные необходимые поля, не охватываемых профилями US Core или Argonaut:

 - Группировка, по крайней мере один элемент с
    - Воспроизведение групп
    - Воспроизведение плана
 - Период
 - SubscriberId

При поиске ресурсов используются метод GET и следующие параметры:

 - Patient = \<patient id>

Другие [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) сведения об этом наборе полей см. в этой области.
