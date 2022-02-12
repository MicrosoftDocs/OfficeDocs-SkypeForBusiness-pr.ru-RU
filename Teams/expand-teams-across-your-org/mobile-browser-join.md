---
title: Управление опытом  присоединиться к Teams виртуальных посещений в мобильных браузерах
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
description: Узнайте о том, как присоединиться к Teams виртуальных посещений в мобильных браузерах.
ms.openlocfilehash: 83bbe6e2db29a1ed43bbe1646f8545072dac7d2d
ms.sourcegitcommit: 2e8daa3511cd198b3e0d43b153dd37a59cb21692
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2022
ms.locfileid: "62763713"
---
# <a name="manage-the-join-experience-for-teams-virtual-visits-on-mobile-browsers"></a>Управление опытом  присоединиться к Teams виртуальных посещений в мобильных браузерах

Microsoft Teams позволяет людям присоединяться к встречам на мобильных устройствах, не скачивать Teams. Для более простого обслуживания участники могут присоединяться к таким встречам, как посещения здравоохранения, финансовые консультации, часы работы преподавателей и так далее, из мобильного браузера. Участникам не нужно устанавливать мобильное приложение Teams на своих мобильных устройствах с Android или iOS.

Когда участник присоединяется к встрече с мобильного устройства, он не может скачать Teams. Вместо этого Teams в мобильном браузере, где участник может выбрать **Присоединиться сейчас**, чтобы присоединиться. Помните, что если Teams уже установлен на мобильном устройстве участника, Teams откроется в мобильном браузере, а не в приложении.

В настоящее время для встреч, запланированных с помощью мобильного браузера, доступны следующие варианты:

- [Приложение Bookings](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-us&rs=en-us&ad=us#PickTab=Bookings)
- Microsoft Teams EHR

  - Интеграция [с EHR Cerner](healthcare/ehr-admin-cerner.md)
  - Интеграция [с EHR](healthcare/ehr-admin.md)

## <a name="set-up-mobile-browser-join"></a>Настройка  присоединиться к мобильному браузеру

### <a name="appointments-scheduled-through-the-bookings-app"></a>Встречи, запланированные с помощью приложения Bookings

Планиры в вашей организации могут включить эту функцию для определенных типов встреч и для отдельных встреч в приложении Bookings.

После того как эта функция будет включена, в подтверждении сообщения электронной почты или SMS,отправленного участникам, будет содержаться ссылка на собрание, которая открывается Teams в мобильном браузере. На мобильных устройствах с Android Teams в Chrome. На мобильных устройствах с iOS Teams в Safari.

#### <a name="turn-on-mobile-browser-join-for-an-appointment-type"></a>Включив мобильное присоединиться к браузеру для типа встречи

В Bookings перейдите в **Параметры** >  Типы назначений **, выберите** тип [встречи, а](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887) затем включив разрешить участникам присоединяться в **мобильном браузере**. Это позволяет присоединяться к мобильным браузерам для всех встреч этого типа.

:::image type="content" source="../media/mobile-browser-join-bookings-appointment-type.png" alt-text="Снимок экрана: параметр "Разрешить участникам присоединяться из мобильного браузера" для типов встреч в приложении Bookings":::

#### <a name="turn-on-mobile-browser-join-for-an-individual-appointment"></a>Включив мобильное присоединиться к браузеру для отдельной встречи

В Bookings выберите **Новое резервирование**, а затем включив разрешить участникам **присоединяться в мобильном браузере**.

:::image type="content" source="../media/mobile-browser-join-bookings-form.png" alt-text="Снимок экрана: параметр "Разрешить участникам присоединяться из мобильного браузера" в новой форме резервирования в приложении Bookings":::

### <a name="appointments-scheduled-through-the-teams-ehr-connector"></a>Встречи, запланированные через Teams EHR

Вы и ваши сотрудники не должны ничего настроить!

**Интеграция с EHR Cerner**. Соединитер Teams EHR поддерживает пациентов, которые присоединяются к виртуальным встречам с помощью мобильных устройств. Во время встречи пациенты могут присоединиться, коснувшись ссылки в SMS-сообщении. Пациент выбирает нужный браузер, а затем Teams в этом браузере.

**Интеграция с EHR**- и Teams EHR поддерживает пациентов, которые присоединяются к виртуальным встречам через Интернет и на мобильных устройствах myChart. Во время встречи пациенты могут начать визит с myChart с помощью кнопки **Виртуальное посещение** . Пациент выбирает нужный браузер, а затем Teams в этом браузере.

## <a name="supported-mobile-browsers"></a>Поддерживаемые браузеры мобильных устройств

Ниже  ниже 2000 мобильных браузеров, которые в настоящее время поддерживаются. Мы поддерживаем последнюю версию плюс две предыдущие версии, если не указано иное.

|Платформа  |Хром |Сафари |Edge (Chromium)|
|---------|:---:|:---:|:---:|
|Android   |   &#x2714;      |         |         |
|iOS    |         |  &#x2714; &sup1;       |         |
|Macos     |         |  &#x2714; &sup2;    |         |

&sup1; Приложения iOS в Safari не могут выбирать устройства микрофона и динамиков. Например, Bluetooth устройств. Это ограничение операционной системы, которая управляет выбором устройства по умолчанию.

&sup2; Для поддержки исходяющих видео требуется Safari 14+ и macOS 11+.

## <a name="things-to-consider"></a>Что необходимо учесть

Сотрудник, который проводит визит, может поделиться своим экраном со своего рабочего Teams, мобильного или веб-клиента с участником, который присоединяется из мобильного браузера. Однако участники не могут делиться своим экраном в мобильном браузере.

> [!NOTE]
> Мы добавляем дополнительные возможности для  присоединиться к собранию в будущих выпусках Teams, поэтому проверяйте эту возможность, чтобы получить самые последние сведения. Чтобы быть в верхней части предстоящих Teams, ознакомьтесь с Microsoft 365 [roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).

## <a name="related-articles"></a>Статьи по теме

- [Виртуальные посещения с Teams и приложением Bookings](bookings-virtual-visits.md)
- [Создание типа встречи в Bookings](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)
- [Присоединиться к встрече с Bookings в качестве участника](https://support.microsoft.com/office/join-a-bookings-appointment-as-an-attendee-95cea12d-2220-421f-a663-6efb20913c7f)
- [Виртуальные посещения с Teams интеграция с EHR Cerner](healthcare/ehr-admin-cerner.md)
- [Виртуальные посещения Teams интеграция с EHR](healthcare/ehr-admin.md)
