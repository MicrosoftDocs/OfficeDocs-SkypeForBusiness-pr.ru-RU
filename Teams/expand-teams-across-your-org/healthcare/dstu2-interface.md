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
ms.openlocfilehash: d29dab88f6ee53eb4c758f6c95f71278e20ecdbe
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766982"
---
# <a name="dstu2-interface-specification"></a>Характеристики интерфейса DSTU2

> [!IMPORTANT]
> **Действующий 30 октября 2020 г. приложение пациентов будет признано устаревшим, и пользователи больше не смогут установить его из магазина App Store. Мы рекомендуем вам приступить к работе с [приложением "списки](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) " в Teams уже сегодня.**
>
>Данные приложения пациентов хранятся в почтовом ящике группы Office 365, которая является резервной командой. Когда приложение пациентов удаляется, все связанные с ним данные будут храниться в этой группе, но к нему больше нельзя будет получить доступ с помощью пользовательского интерфейса. Текущие пользователи могут повторно создавать свои списки с помощью [приложения "списки](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)".
>
>[Приложение "списки](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) " предустановлено для всех пользователей Teams и доступно в виде вкладки в каждой команде и канале. С помощью списков группы работоспособности могут создавать списки пациента с использованием встроенного шаблона пациентов, с нуля или путем импорта данных в Excel. Дополнительные сведения об управлении приложением Lists в Организации можно найти в разделе [Управление приложением "списки"](../../manage-lists-app.md).

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Настройка или перенастройка сервера FHIR для работы с приложением Microsoft Teams пациентов требует понимания данных, к которым приложению требуется доступ. Сервер FHIR должен поддерживать запросы POST, используя пакеты для указанных ниже ресурсов.

- [Подождите](#patient)
- [Наблюдение](#observation)
- [Условие](#condition)
- [Происходит](#encounter)
- [Недопустимый Allergy](#allergyintolerance)
- [Приложения](#coverage)
- [Лечения заказ](#medication-order)
- [Расположение](#location)

> [!NOTE]
> Ресурс пациент является единственным обязательным ресурсом (без которого приложение не будет загружаться вообще). Тем не менее, рекомендуется, чтобы партнеры реализовали поддержку всех вышеупомянутых ресурсов для спецификаций, указанных ниже, для наилучшего взаимодействия с пользователем в приложении Microsoft Teams пациентов.

Запросы из приложения Microsoft Teams пациентов для нескольких ресурсов. отправляет набор (пакет) запросов на URL-адрес сервера FHIR. Сервер обрабатывает каждый запрос и возвращает набор ресурсов, соответствующих каждому запросу. Дополнительные сведения и примеры можно найти в разделе [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .

Все перечисленные ниже ресурсы FHIR должны быть доступны по прямой ссылке на ресурс.

## <a name="conformance-minimum-required-field-set"></a>Минимальный набор полей, необходимый для установки соответствия

 Сервер FHIR должен реализовать инструкцию соответствия, чтобы получить сводную информацию о ее возможностях factual. Ниже перечислены параметры на сервере DSTU2 FHIR:

 - ДЕРЖИВАЕТ

    - Режиме
    - Действует
    - Ресурс: тип
    - Безопасность: [расширение URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
   
 - FhirVersion (для нашего кода требуется, чтобы узнать, в какую версию следует поворачивать, так как мы поддерживаем несколько версий.)

[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)Дополнительные сведения об этом множестве полей приведены в разделе.

## <a name="patient"></a>Подождите

Это минимальные обязательные поля, которые являются подмножеством полей [профиля пациента Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :

 - Family (имя)
 - Name (имя). задано
 - Полу
 - Рождения
 - MRN (идентификатор)

В дополнение к полям Argonaut для удобства пользователей приложение пациентов также считывает следующие поля:

 - Name. use
 - Name. prefix
 - CareProvider (эта ссылка на ресурс пациент должна содержать отображаемые поля, показанные в приведенном ниже примере).

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

Поиск ресурсов использует метод POST по адресу/Patient/_search и следующие параметры:

 - номер
 - Семья: Contains = (ищет все пациентов, чье имя семейства оно содержат.)
 - указанный =\<substring>
 - Name =\<substring>
 - Дата рождения = (точное совпадение)
 - \_Count (максимальное количество возвращаемых результатов) <br> Ответ должен содержать общее количество записей, возвращенных в результате поиска, и \_ количество будет использоваться PatientsApp для ограничения количества возвращенных записей.
 - Идентификатор =\<mrn>

Цель — найти и отфильтровать пациента в пациент, выполнив следующие действия:

- ID: это идентификатор ресурса, который содержит каждый ресурс в FHIR.
- MRN: фактический идентификатор пациента, который будет знать Clinical сотрудника. Мы понимаем, что этот MRN основывается на типе идентификатора в ресурсе идентификатора в FHIR
- Имя
- Рождения

Ниже приведен пример этого звонка.

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

[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)Дополнительные сведения об этом множестве полей приведены в разделе.

## <a name="observation"></a>Наблюдение

Это минимальные обязательные поля, которые являются подмножеством профиля Argonaut важную подпись:

 - Эффективная (Дата и время)
 - Код. кодирование. Code
 - ValueQuantity. Value

В дополнение к полям Argonaut для удобства пользователей приложение пациентов также считывает следующие поля:

 - Код. программирование. Display
 - ValueQuantity. ед.

При использовании наблюдения за компонентами одна и та же логика применяется для наблюдения за каждым компонентом.

Поиск ресурсов использует метод GET и следующие параметры:

 - пациент =\<patient id\>
 - сортировка: DESC =\<field ex. date\>

Цель состоит в том, чтобы получить последние важные знаки для пациента, [VitalSigns. DSTU. saz] (наблюдение?).

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

[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)Дополнительные сведения об этом множестве полей приведены в разделе.

## <a name="condition"></a>Условие

Это минимальные обязательные поля, которые являются подмножеством [профиля условия Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):

1. Код. кодирование [0]. Показан

В дополнение к полям Argonaut для удобства пользователей приложение пациентов также может прочитать следующие поля:

 - Дата записи
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

[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)Дополнительные сведения об этом множестве полей приведены в разделе.

## <a name="encounter"></a>Происходит

Это минимальные обязательные поля, которые являются подмножеством подмножества для основного профиля в США, которое должно иметь следующие поля:

 - Состояни
 - Введите [0]. Кодирование [0]. Показан

Кроме того, ниже перечислены поля, которые можно получить из основного приложения US "требуется поддержка".

 - Period. Start
 - Расположение [0]. Расположение. Display

Поиск ресурсов использует метод GET и следующие параметры:

 - пациент =\<patient id>
 - _sort: DESC =\<field ex. date>
 - _count =\<max results>

Цель — получить Последнее известное расположение пациента. Каждый из этих обнаружений ссылается на ресурс расположения. Ссылка также должна включать поле отображения местоположения. Ниже приведен пример этого звонка.

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

[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)Дополнительные сведения об этом множестве полей приведены в разделе.

## <a name="allergyintolerance"></a>AllergyIntolerance

Это минимальные обязательные поля, которые являются подмножеством профиля Argonaut AllergyIntolerance:

 - Code. Text
 - Код. кодирование [0]. Показан
 - Состояни

В дополнение к полям Argonaut для удобства пользователей приложение пациентов также считывает следующие поля:

 - RecordedDate
 - Примечание. текст
 - Реакция [..]. Вещество. текст
 - Реакция [..]. Манифест [..]. Текстовые
 - Text. Div

Поиск ресурсов использует метод GET и следующие параметры:

 - Пациент =  \<patient id>

Ниже приведен пример этого звонка:

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

[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)Дополнительные сведения об этом множестве полей приведены в разделе.

## <a name="medication-order"></a>Лечения заказ

Это минимальные обязательные поля, которые являются подмножеством профиля Argonaut MedicationOrder:

 - DateWritten
 - Предписанный. Display
 - Лечения. Display (если ссылка)
 - Лечения. Text (если понятие)

В дополнение к полям Argonaut для удобства пользователей приложение пациентов также может прочитать следующие поля:

 - DateEnded
 - DosageInstruction. Text
 - Text. Div

Поиск ресурсов использует метод GET и следующие параметры:

 - пациент =\<patient id>
 - _count =\<max results>

Ниже приведен пример этого звонка:

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

[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)Дополнительные сведения об этом множестве полей приведены в разделе.

## <a name="coverage"></a>Приложения

Это минимальный обязательный набор полей, не охваченных профилями США или Argonaut:

 - Payor

Поиск ресурсов использует метод GET и следующие параметры:

 - пациент =\<patient id>

Ниже приведен пример этого звонка:

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
    
[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)Дополнительные сведения об этом множестве полей приведены в разделе.

## <a name="location"></a>Местоположение

Этот ресурс используется только в качестве ссылки на ресурс " [встреча](#encounter) ".

[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)Дополнительные сведения об этом множестве полей приведены в разделе.
