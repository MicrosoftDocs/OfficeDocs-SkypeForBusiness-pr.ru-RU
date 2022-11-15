---
title: Планирование трансляций в Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: sonua
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
- highpri
search.appverid: MET150
description: В этой статье вы ознакомитесь с факторами, которые следует учитывать перед настройкой трансляций в Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1bbc6452847182533271f4aa7c7652ff8b00ba3
ms.sourcegitcommit: 73b13cd8a79ba1724b9fb79c8356a7cacafb7dd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2022
ms.locfileid: "68966318"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Планирование трансляций в Microsoft Teams

При планировании трансляций в Teams для проведения крупных собраний в организации необходимо учесть ряд факторов перед началом настройки.

> [!Note]
> For details about Teams live events on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3). See [prepare your organization](../prepare-network.md) to learn about bandwidth requirements for Teams live events.

## <a name="who-can-attend-create-and-schedule-live-events"></a>Кто может посещать, создавать и планировать трансляции

Anyone can attend a live event without a license. Read [Admin quick start - Meetings and live events](../quick-start-meetings-live-events.md).

Следующие предварительные условия необходимы для пользователя, чтобы запланировать живое событие Команды.

Ниже перечислены лицензии, которые необходимы для организации, создания или показа трансляций Teams.  

- **Для организации:** лицензия Microsoft или Office 365 корпоративный E1, E3 или E5 **[либо]** лицензия Microsoft или Office 365 для образования A3 или A5. 
- **To produce or present:** A Microsoft or Office 365 Enterprise E1, E3 or E5 license, **[or]** a Microsoft or Office 365 Education A1, A3 or A5 license. The exception to this requirement is guest users can present without a license if the other criteria for [guest users](plan-for-teams-live-events.md#guest-to-present) is met.
- Лицензия Microsoft Teams включена в лицензии, перечисленные в первом и втором маркерах.
- Если вы планируете предоставлять общий доступ к контенту для внешнего приложения или устройства, потребуется лицензия Microsoft Stream —. см. [Лицензирование Microsoft Stream](/stream/license-overview). Лицензия Stream не требуется, если для создания события используются новые службы Кодировщика Teams. 

  Users won't need a Microsoft Stream license assigned if you want users to only record and download the recordings. This will mean that the recordings aren't stored in Microsoft Stream but are instead stored in Azure Media Services (AMS) with a 180-day limit before it's deleted. It's not something at this point that an admin can control or manage to include the ability to delete it.

>[!Note]
> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to OneDrive for Business and SharePoint for meeting recordings.

> [!NOTE]
> В настоящее время не существует планов Microsoft 365 для малого бизнеса, которые можно использовать для создания и хранения трансляций Teams.

Важно знать, что в зависимости от используемого метода работы для участия в трансляции в качестве пользователя, прошедшего проверку подлинности, нужна лицензия Microsoft 365 или Office 365.

- **Для событий, созданных в Teams или с помощью кодировщика На основе Teams**  Пользователю должна быть назначена лицензия Teams.
- **Для событий, создаваемых с помощью внешнего приложения или устройства**. Пользователю должна быть назначена лицензия Stream.

> [!NOTE]
> Мероприятия в прямом эфире Teams теперь доступны для организаций облачного сообщества правительства США (GCC).

Для получения дополнительной информации о лицензировании см. [Дополнительное лицензирование Microsoft Teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

У пользователя должны быть:

- Расписание личных встреч в Teams включено (*параметр TeamsMeetingPolicy -AllowPrivateMeetingScheduling = True*).
- Общий доступ к видео включен на собраниях Teams (*параметр TeamsMeetingPolicy -AllowIPVideo = True*).
- Совместное использование экрана включено в собраниях Teams (*параметр TeamsMeetingPolicy -ScreenSharingMode = EntireScreen*).
- Оперативное планирование событий в Teams включено (*параметр TeamsMeetingBroadcastPolicy -AllowBroadcastScheduling = True*).
- Разрешения на создание живых событий в Stream (для внешнего приложения или устройства производства).
- Режим сосуществования настроен на поддержку планирования собраний Teams (*"Острова", "Сначала собрания" или "Только Teams"*).

> [!IMPORTANT]
> Анонимные пользователи, не прошедшие проверку подлинности, не могут быть приглашены в качестве продюсеров или докладчиков на живых мероприятиях Команд.

### <a name="guest-to-present"></a>[Гостевой показ](#guest-to-present)

Для выступления гостя в трансляции необходимо выполнить следующие задачи:

1. [Добавьте пользователя в качестве гостя в команду](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. Пользователь должен принять гостевое приглашение и присоединиться к команде.
3. [Запланируйте трансляцию и добавьте гостя в свою группу события](https://support.microsoft.com/article/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).

As a best practice, we recommend that you create a channel for producers and presenters of the live event so they can chat and share information before the event. Guests who don't have Microsoft 365 credentials won't see the Calendar in Teams. To make it easy for them to join the event, producers can post the event link to the channel. Presenters can then open Teams, go to the channel, and then select the link to join the event.

## <a name="who-can-watch-live-events"></a>Кто может смотреть трансляции

| Видимость участников | Производство Teams | Производство внешнего приложения или устройства | Кодировщик На основе Teams
|------------------------------|-----------------|----------------------|----------------|
|Общедоступно (анонимные пользователи)      |  Да            |  Нет                  | Да
|Гостевые пользователи                   |  Да<sup>1</sup>            |  Нет                  |  Да            |
|Все пользователи в компании внешнего доступа (федерации) |  Да<sup>1</sup>|  Нет                  | Да            |
|Все в компании           |  Да            |  Да                 | Да                |
|Конкретные группы / люди      |  Да            |  Да                 | Да                |

<sup>1</sup> Можно пригласить только при использовании параметра "Участники и группы" <br>

## <a name="teams-live-events"></a>Трансляции Teams

В следующей таблице перечислены основные возможности и функции, предлагаемые в трансляциях

> [!IMPORTANT]
> **Повышение предельных значений для трансляций Microsoft 365**
>
> **Чтобы продолжить поддерживать потребности наших клиентов, мы продлеваем временное увеличение ограничений на прямые трансляции до 31 декабря 2022 г., в том числе:**:
>
>- Поддержка событий для до 20 000 участников
>- 50 одновременных трансляций в клиенте
>- Длительность события — 16 часов на трансляцию
>
> Additionally, live events with up to 100,000 attendees can be planned through the Microsoft 365 live events assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions). 

| Возможность | Трансляция собрания Skype | События, организованные в Teams | События, организованные во внешнем приложении или на устройстве |
|---------|---------|---------|---------|
|Максимальный размер аудитории |10 000 участников |10 000 участников<sup>1</sup> |10 000 участников<sup>1</sup> |
|Максимальная продолжительность живого события |4 часа |4 часа |4 часа |
|Максимальное количество докладчиков и организаторов в трансляции |10 <sup>2</sup> |10 <sup>2</sup> |10 <sup>2</sup> |
|Максимальное количество одновременных трансляций на одну организацию, использующую Microsoft 365 или Office 365 |15  | 15  | 15  |
|Создание живых событий |   Портал широковещательного показа собраний Skype |Teams, Yammer через Teams | Teams, Yammer через Teams, Stream |
|Участие аудитории - Yammer |&#x2714; |&#x2714;(интегрированный интерфейс) |&#x2714;(интегрированный интерфейс) |
|Участие аудитории - Модерируемые вопросы и ответы |&#x2714;  |&#x2714; |&#x2714; |
|Клиент продюсер на Windows |&#x2714;(Skype для бизнеса) |&#x2714; (Teams) |&#x2714; (Stream, Teams через Stream Embed) |
|Клиент продюсер на Mac |&#x274C;  | &#x2714; (Teams) |&#x2714; (Stream, Teams через Stream Embed) |
|Количество посетителей в интерфейсе Producer |&#x274C;  |&#x2714; (Teams) |&#x2714; (Stream, Teams через Stream Embed) |
|Позволяет нескольких докладчиков |&#x2714;(Skype для бизнеса) |&#x2714; (Teams) |Н/Д  |
|Пригласите докладчика во время встречи |&#x2714;(Skype для бизнеса) |&#x274C; |Н/Д |
|Присоединение докладчика в Интернете и на мобильных устройствах |&#x2714;(Skype для бизнеса)  |&#x274C; |Н/Д |
|Докладчики и участники с внешним доступом (федерацией) и гостевым доступом |&#x2714;(Skype для бизнеса)  |  &#x2714; (Teams) |Н/Д |
|Докладчик — доступ к ТСОП |&#x274C; |&#x2714; (Teams) |Недоступно |
|Показ экрана |&#x274C; |&#x2714; (Teams) |Н/Д |
|Доступ к системным звукам в Windows (доступно только при демонстрации экрана)|&#x274C; |&#x2714; (Teams) |&#x2714; |
|Презентация PowerPoint (общий доступ к PPT) |&#x2714; |&#x274C; (вместо этого можно использовать демонстрацию экрана) |Н/Д |
|Запись собраний на основе облачных технологий |&#x2714; |&#x2714; |&#x2714; |
|Автоматическая публикация записи в поток |&#x274C; |&#x274C; |&#x2714; |
|Автоматические субтитры |&#x2714; |&#x2714; |&#x274C; |
|Подписи в записи живых событий |&#x2714; |&#x2714; |&#x2714; |
|Attendee DVR управления (пауза, перемотка) |&#x2714; |&#x2714; |&#x2714; |
|ECDN Майкрософт |&#x274C; |&#x2714; |&#x2714; |
|Партнерская поддержка eCDN |&#x2714; (Kollective, Hive, Riverbed) |&#x2714; (Kollective, Hive, Ramp, Riverbed) |&#x2714; (Hive, Kollective, Ramp, Riverbed) |
|Отчет о посещаемости после трансляции для продюсеров |&#x2714; |&#x2714; |&#x274C; |
|Анализ настроений аудитории - Голосование в реальном времени и опросы |&#x2714; (Microsoft Pulse) |&#x274C; |&#x274C; |

<sup>1</sup> The limits that are set might be changed. Check [Limits and specifications for Teams](../limits-specifications-teams.md).<br/>
<sup>2</sup> Вы можете использовать до 100 докладчиков и организаторов в трансляции, но в списке отображаются только последние 10 выступавших.

## <a name="regional-availability"></a>Доступность в регионах

You can use Teams live events in multiple regions across the world. The following information shows availability for event team members and attendees.

> [!IMPORTANT]
> Регион для мероприятия выбирается автоматически в зависимости от организатора и местоположения арендатора Microsoft 365.

**Доступно в этих региональных дата-центрах**

- Северная Америка
- Центральная Америка
- Южная Америка
- Азиатско-Тихоокеанский регион
- Европа / Африка

**Расположение данных для этих стран или регионов (поддерживается)**

- Австралия
- Бразилия
- Канада
- Франция
- Германия
- Индия
- Япония
- Норвегия
- Сингапур
- Южная Африка
- Южная Корея
- Швейцария
- ОАЭ
- Великобритания

**Исключения и рекомендации**

- **Расположение данных:** расположения данных Teams, за исключением перечисленных выше, в настоящее время не поддерживаются.

## <a name="next-steps"></a>Дальнейшие действия

Перейдите в раздел [Настройка для командных турниров](set-up-for-teams-live-events.md).

### <a name="related-topics"></a>Статьи по теме

- [Что такое трансляции Teams?](what-are-teams-live-events.md)
- [Настройка прямых трансляций Teams](set-up-for-teams-live-events.md)
- [Настройка параметров живых событий в Teams](configure-teams-live-events.md)
