---
title: 'Краткое руководство для администраторов: собрания и трансляции в Microsoft Teams'
ms.reviewer: ''
description: Краткое руководство для администраторов о получении соответствующих лицензий, развертывании и настройке собраний по сети и трансляций в Microsoft Teams.
ms.topic: article
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
- m365initiative-meetings
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3b793eb5124a9105a718accc5767493aa9c35fbc
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031635"
---
# <a name="admin-quick-start---meetings-and-live-events-in-microsoft-teams"></a>Краткое руководство для администраторов: собрания и трансляции в Microsoft Teams

В Microsoft Teams существует 2 способа общения: собрания и трансляции. Воспользуйтесь этой статьей, чтобы быстро развернуть и настроить собрания и трансляции для своей организации.

> [!Note]
> Подробные сведения о быстрой настройке собраний и трансляций Teams на разных платформах см. в статье [Возможности Teams на разных платформах](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

 - **Собрания** в Teams поддерживают передачу звука и видео, а также демонстрацию экрана для 300 пользователей. И вам не нужно быть участником организации (и вам даже не нужна учетная запись Teams!), чтобы присоединиться к собранию Teams. Просто просмотрите в приглашении инструкции о присоединении.

 - **Трансляции** — это расширение собраний Teams, с помощью которого можно планировать и проводить мероприятия с трансляцией для крупных аудиторий (до 10 000 пользователей) в Интернете. Если вам требуется провести собрание для более чем 300 человек, используйте трансляцию.

## <a name="get-licenses-for-meetings-and-live-events"></a>Получение лицензий для собраний и трансляций

Любой может бесплатно посетить собрание или открытую трансляцию Teams — лицензия не требуется. Участники могут присоединиться к собранию и трансляции Teams, нажав кнопку **Присоединиться** в Teams или в приглашении на собрание. Звук собрания — это часть собрания Teams, но если вы хотите, чтобы пользователи могли подключиться к собранию по телефону, потребуется указать номер телефона для подключения.

Пользователям, организующим, планирующим и проводящим собрания или трансляции, потребуется одна из лицензий Microsoft 365 или Office 365, указанных в таблице ниже. Если вы уже используете Teams, возможно, у вас есть лицензия, необходимая для организации и проведения собраний и трансляций.

:::image type="content" source="media/quick-start-meetings-live-events-image1.png" alt-text="Таблица с лицензиями, требующимися для собраний и трансляций Teams":::

> <sup>1</sup> У организаторов собраний должна быть [лицензия для надстройки аудиоконференций](teams-add-on-licensing/microsoft-teams-add-on-licensing.md), чтобы отправлять приглашения, содержащие телефонные номера для подключения к конференции.
>
> <sup>2</sup> Для подключения к собранию с помощью функции [**Позвонить мне на** номер](set-up-the-call-me-feature-for-your-users.md) требуется, чтобы у организаторов была лицензия E5 или [лицензия для надстройки аудиоконференций](teams-add-on-licensing/microsoft-teams-add-on-licensing.md). Также может потребоваться [абонентская группа](what-are-dial-plans.md).

Чтобы узнать больше о лицензировании, прочтите [описание службы Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).

## <a name="make-sure-your-networks-ready"></a>Проверка готовности сети

Если вы уже подготовили свою сеть при развертывании Microsoft 365 или Office 365, возможно, у вас все настроено. В любом случае, особенно если вы быстро развертываете Teams в качестве первой рабочей нагрузки Office 365 для поддержки **удаленных сотрудников** , ознакомьтесь со статьей [Подготовка сети организации к использованию Teams](prepare-network.md), чтобы убедиться в своей готовности.

## <a name="meetings-and-conferencing"></a>Собрания и конференции

- В качестве администратора вы настроите [параметры собраний](meeting-settings-in-teams.md) для всех пользователей. Затем вы примените [политики собраний](meeting-policies-in-teams.md) для выбора функций, доступных (и недоступных) пользователям.

- Дополнительные сведения об управлении записью собраний приведены в статье [Запись облачного собрания в Teams](cloud-recording.md).

- Если ваши пользователи впервые применяют собрание Teams, поделитесь с ними учебным курсом [Управление собраниями](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4). Ознакомьтесь с нашим онлайн-занятием под руководством инструктора [Проведение эффективных собраний в Teams](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings).

- Сведения об управлении параметрами собраний см. в статье [Изменение параметров участников для собраний Teams](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e).

- Не забудьте об [управлении устройствами пользователей](device-management.md) — телефонами, гарнитурами и камерами. Чтобы получить актуальные сведения об устройствах, сертифицированных для Teams, перейдите в раздел [Устройства Teams](https://office.com/teamsdevices).

## <a name="live-events"></a>Трансляции

- Как и для собраний, вы в качестве администратора [настраиваете трансляции](teams-live-events/configure-teams-live-events.md) для всех пользователей. Затем настройте (и назначьте) [политики трансляций](teams-live-events/set-up-for-teams-live-events.md) для выбора доступных (и недоступных) возможностей для пользователей.

- Обеспечьте подготовку инициаторов и организаторов трансляций — отправьте их на страницу [Начало работы с трансляциями](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a).

- Если вы еще не работали с трансляциями, ознакомьтесь со статьями [Что такое трансляции Teams?](teams-live-events/what-are-teams-live-events.md) и [Планирование трансляций Teams](teams-live-events/plan-for-teams-live-events.md).

## <a name="related-topics"></a>Статьи по теме

[Собрания и конференции в Teams](deploy-meetings-microsoft-teams-landing-page.md)

[Аудиоконференции в Teams](deploy-audio-conferencing-teams-landing-page.md)

[Трансляции в Teams](teams-live-events/what-are-teams-live-events.md)

[Ограничения и спецификации для Teams](limits-specifications-teams.md)

[Техническое сообщество Майкрософт: трансляции в Microsoft 365](https://resources.techcommunity.microsoft.com/live-events/)
