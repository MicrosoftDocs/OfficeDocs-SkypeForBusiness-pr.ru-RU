---
title: Управление опытом join для Teams виртуальных посещений в мобильных браузерах
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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: hafarmer
description: Узнайте о том, как присоединиться к Teams в мобильных браузерах.
ms.openlocfilehash: 4017947d53078b33ce2a4195a6ace9af92adc85c
ms.sourcegitcommit: 1c2364fbefd95151f0847a35e8bc7c4c1b3892f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2021
ms.locfileid: "58936153"
---
# <a name="manage-the-join-experience-for-teams-virtual-visits-on-mobile-browsers"></a>Управление опытом join для Teams виртуальных посещений в мобильных браузерах

Microsoft Teams позволяет людям присоединяться к встречам на мобильных устройствах без необходимости скачивать Teams. Для более простого обслуживания участники могут присоединяться к таким встречам, как посещения здравоохранения, финансовые консультации, часы работы преподавателей и так далее из мобильного браузера. Участникам не нужно устанавливать мобильное приложение Teams на своих мобильных устройствах с Android или iOS.

Когда участник присоединяется к встрече с мобильного устройства, он не может скачать Teams. Вместо этого Teams в мобильном браузере, где участник может выбрать Присоединиться **сейчас,** чтобы присоединиться. Помните, что если Teams уже установлен на мобильном устройстве участника, Teams откроется в мобильном браузере, а не в приложении.

В настоящее время для встреч, запланированных с помощью мобильного браузера, доступны следующие варианты:

- [Приложение Bookings](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-us&rs=en-us&ad=us#PickTab=Bookings)
- [Microsoft Teams Соединитектор электронных медицинских записей (EHR)](healthcare/ehr-admin.md)

## <a name="set-up-mobile-browser-join"></a>Настройка присоединиться к мобильному браузеру

### <a name="appointments-scheduled-through-the-bookings-app"></a>Встречи, запланированные с помощью приложения Bookings

Планиры в вашей организации могут включить эту функцию для определенных типов встреч и для отдельных встреч в приложении Bookings.

После того как эта функция будет включена, в сообщении с подтверждением или SMS-сообщении, отправленным участникам, будет содержаться ссылка на собрание, которая открывается Teams в мобильном браузере. На мобильных устройствах с Android Teams в Chrome. На мобильных устройствах с iOS Teams в Safari.

#### <a name="turn-on-mobile-browser-join-for-an-appointment-type"></a>Включить мобильное присоединиться к браузеру для типа встречи

В Bookings перейдите в **Параметры** типы встреч , выберите тип встречи , а затем включив разрешить участникам присоединяться в  >   **мобильном браузере**. [](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887) Это позволяет присоединяться к мобильным браузерам для всех встреч этого типа.

:::image type="content" source="../media/mobile-browser-join-bookings-appointment-type.png" alt-text="Снимок экрана: параметр "Разрешить участникам присоединяться" в мобильном браузере для типов встреч в приложении Bookings":::

#### <a name="turn-on-mobile-browser-join-for-an-individual-appointment"></a>Включить мобильное присоединиться к браузеру для отдельной встречи

В Bookings выберите **Новое резервирование**, а затем включив разрешить участникам **присоединяться в мобильном браузере.**

:::image type="content" source="../media/mobile-browser-join-bookings-form.png" alt-text="Снимок экрана: параметр "Разрешить участникам присоединяться из мобильного браузера" в новой форме резервирования в приложении Bookings":::

### <a name="appointments-scheduled-through-the-teams-ehr-connector"></a>Встречи, запланированные через Teams EHR

Вы и ваши сотрудники не должны ничего настроить!

Соединит Teams EHR поддерживает пациентов, которые присоединяются к виртуальным посещениям через MyChart и мобильные устройства. Во время встречи пациенты могут начать виртуальное посещение из myChart с помощью кнопки Начать **виртуальное посещение.** Пациент выбирает нужный браузер, а затем Teams в этом браузере.

## <a name="supported-mobile-browsers"></a>Поддерживаемые браузеры мобильных устройств

Ниже ются мобильные браузеры, которые в настоящее время поддерживаются. Мы поддерживаем последнюю версию и две предыдущие версии, если не указано иное.

|Платформа  |Хром |Сафари |Edge (Chromium)|
|---------|:---:|:---:|:---:|
|Android   |   &#x2714;      |         |         |
|iOS    |         |  &#x2714; &sup1;       |         |
|Macos     |         |  &#x2714; &sup2;    |         |

&sup1; Приложения iOS в Safari не могут выбирать устройства микрофона и динамиков. Например, Bluetooth устройств. Это ограничение операционной системы, которая управляет выбором устройства по умолчанию.

&sup2; Для поддержки исходяющих видео требуется Safari 14+ и macOS 11+.

> [!NOTE]
> Мы добавляем дополнительные возможности для присоединиться к собранию в будущих выпусках Teams, поэтому проверяйте эту возможность, чтобы получить самые последние сведения. Чтобы быть в верхней части предстоящих Teams, ознакомьтесь с Microsoft 365 [roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).

## <a name="related-articles"></a>Статьи по теме

- [Виртуальные посещения с Teams и приложением Bookings](../bookings-app-admin.md)
- [Создание типа встречи Bookings](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)
- [Присоединиться к встрече Bookings в качестве участника](https://support.microsoft.com/office/join-a-bookings-appointment-as-an-attendee-95cea12d-2220-421f-a663-6efb20913c7f)
- [Виртуальные посещения с помощью Teams — интеграция с электронными медицинскими картами](healthcare/ehr-admin.md)
