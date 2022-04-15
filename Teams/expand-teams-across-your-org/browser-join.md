---
title: Управление интерфейсом присоединения для Teams виртуальных встреч в браузерах
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: hafarmer
description: Узнайте о возможностях присоединения Teams виртуальных встреч в браузерах.
ms.openlocfilehash: 418186734befa66f145ca56f883605715d83aa30
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853310"
---
# <a name="manage-the-join-experience-for-teams-virtual-appointments-on-browsers"></a>Управление интерфейсом присоединения для Teams виртуальных встреч в браузерах

Microsoft Teams упрощает присоединение пользователей к виртуальным встречам без необходимости скачивать Teams. Для более удобного взаимодействия участники могут присоединяться к встречам, таким как визиты в сфере здравоохранения и финансовые консультации из настольного или мобильного браузера. Участникам не нужно устанавливать приложение Teams на своем устройстве.

При присоединении к браузеру, когда участник присоединяется к встрече, ему не предлагается скачать Teams. Вместо этого Teams в браузере, где участник может выбрать "Присоединиться **сейчас"**, чтобы присоединиться. При использовании этой функции следует помнить, что если Teams уже установлен на устройстве, Teams откроется в браузере, а не в приложении.

В настоящее время присоединение к браузеру доступно для встреч, запланированных с помощью следующих параметров:

- [Приложение Bookings](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5)
- Microsoft Teams электронной медицинской записи (EHR)

  - Интеграция [с Cerner EHR](healthcare/ehr-admin-cerner.md)
  - Интеграция с [Epic EHR](healthcare/ehr-admin.md)

## <a name="set-up-browser-join"></a>Настройка присоединения к браузеру

### <a name="appointments-scheduled-through-the-bookings-app"></a>Встречи, запланированные через Bookings приложения

Планировщики в организации могут включить эту функцию для определенных типов встреч и для отдельных встреч в Bookings приложения.

После включения этой функции сообщение электронной почты с подтверждением или SMS-сообщение, отправляемое участникам, будет содержать ссылку на присоединение к собранию, которая открывается Teams в браузере для настольных компьютеров или мобильных устройств. Список поддерживаемых браузеров см. в [разделе "Поддерживаемые браузеры"](#supported-browsers).

#### <a name="turn-on-browser-join-for-an-appointment-type"></a>Включение присоединения к браузеру для типа встречи

В Bookings перейдите к **Параметры** >  **Appointment**, выберите тип [встречи, а](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887) затем включите разрешение участникам присоединяться **из браузера**. Это позволяет присоединяться к браузеру для всех встреч этого типа.

:::image type="content" source="../media/browser-join-bookings-appointment-type.png" alt-text="Снимок экрана: разрешение участникам присоединяться из параметра браузера для типов встреч в Bookings приложения":::

#### <a name="turn-on-browser-join-for-an-individual-appointment"></a>Включение присоединения к браузеру для отдельной встречи

В Bookings выберите **"Создать** резервирование", а затем включите параметр "Разрешить участникам **присоединяться из браузера"**.

:::image type="content" source="../media/browser-join-bookings-form.png" alt-text="Снимок экрана: разрешение участникам присоединяться из параметра браузера в новой форме резервирования в Bookings приложения":::

### <a name="appointments-scheduled-through-the-teams-ehr-connector"></a>Встречи, запланированные через соединитель Teams EHR

Вам или вашим сотрудникам не требуется никаких настроек!

**Интеграция с Cerner EHR**. Соединитель Teams EHR поддерживает присоединение пациентов к виртуальным встречам через ссылку в sms-текстовом сообщении. Во время встречи пациенты могут присоединиться, коснувшись ссылки в текстовом сообщении SMS, Teams откроется в браузере.

**Интеграция с Epic EHR**: соединитель Teams EHR поддерживает присоединение пациентов к виртуальным встречам через Интернет и мобильные устройства MyChart. Во время встречи пациенты могут начать встречу из MyChart с помощью кнопки "Начать виртуальное посещение", Teams откроется в браузере.

## <a name="supported-browsers"></a>Поддерживаемые браузеры

Ниже приведены поддерживаемые в настоящее время браузеры. Мы поддерживаем последнюю версию и две предыдущие версии, если не указано иное.

|Платформа  |Хром |Сафари |Edge (Chromium)|
|---------|:---|:---|:---:|
|Android   | &#x2714; &sup1;      |         |         |
|iOS    |         | &#x2714; &sup1; &sup2; |         |
|macOS     | &#x2714; | &#x2714;|         |
|Windows    | &#x2714; |   | &#x2714; |
|Ubuntu/Linux     | &#x2714;         |     |         |

&sup1; Исходящий общий доступ к экрану не поддерживается в iOS или Android.

&sup2; Приложения iOS в Safari не могут выбирать устройства микрофона и динамика. Например, Bluetooth устройства. Это ограничение операционной системы, которая управляет выбором устройства по умолчанию.

## <a name="things-to-consider"></a>Что следует учитывать

Сотрудник, который проводит встречу, может поделиться своим экраном с рабочего стола Teams мобильного или веб-клиента с участником, который присоединяется к рабочему столу или мобильному браузеру. Однако участники не могут делиться своим экраном с рабочего стола или мобильного браузера.

## <a name="related-articles"></a>Статьи по теме

- [Виртуальные встречи с Teams и Bookings приложения](bookings-virtual-visits.md)
- [Создание типа Bookings встречи](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)
- [Присоединение Bookings к собранию в качестве участника](https://support.microsoft.com/office/join-a-bookings-appointment-as-an-attendee-95cea12d-2220-421f-a663-6efb20913c7f)
- [Виртуальные встречи с Teams — интеграция с Cerner EHR](healthcare/ehr-admin-cerner.md)
- [Виртуальные встречи с Teams — интеграция в EHR для ситуаций](healthcare/ehr-admin.md)
