---
title: Знакомство с Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: serdars
description: Найдите подходящий способ развертывания Microsoft Teams в вашей организации. Сведения об инфраструктуре Teams и использовании Teams вместе с Microsoft 365 или Office 365.
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.allteamsdocuments
- intro-overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6ffdae377d1b39e40ad0fc89857c773ac843da38
ms.sourcegitcommit: 50ae550b738424b35df1636590831e6c124ca0c1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/14/2022
ms.locfileid: "68576435"
---
# <a name="welcome-to-microsoft-teams"></a>Знакомство с Microsoft Teams
Эта статья предназначена для администраторов Microsoft Teams в вашей организации. Когда вы будете готовы приступить к работе с Teams, начните со статьи [Как развернуть Teams](./deploy-overview.md) и [Настройка безопасной совместной работы с помощью Microsoft 365 и Microsoft Teams](/microsoft-365/solutions/setup-secure-collaboration-with-teams).

Если вы еще не знакомы с Teams и хотите узнать больше, посмотрите наше короткое видео [Добро пожаловать в Teams](https://www.youtube.com/embed/s3aQV3T0D6c) (55 секунд).

Не пропустите наше видео "Добро пожаловать в Teams" для администраторов Teams (чуть больше 3 минут):

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE47cdp]

If you're looking for end user Teams Help, click **Help** on the left side of the app, or go to the [Microsoft Teams help center](https://support.office.com/teams). For training, go to [Microsoft Teams Training](training-microsoft-teams-landing-page.md). 

## <a name="teams-architecture"></a>Архитектура Teams

В основе Teams лежат группы Microsoft 365 и Microsoft Graph. Teams обеспечивает такой же высокий корпоративный уровень безопасности, соответствия требованиям и управляемости, что и остальные средства Microsoft 365 и Office 365. Teams использует удостоверения, хранящиеся в Azure Active Directory (Azure AD). Работа в Teams продолжается, даже если вы не подключены к сети или в условиях нестабильной работы сети.

Чтобы увидеть, где находится Teams в контексте Microsoft 365, ознакомьтесь с плакатом по архитектуре: [Teams в составе Microsoft 365](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

При создании команды создаются следующие объекты:
- Новая [группа Microsoft 365](office-365-groups.md)
- Сайт [SharePoint Online](sharepoint-onedrive-interact.md) и библиотека документации для хранения файлов команды
- Общий почтовый ящик и календарь [Exchange Online](exchange-teams-interact.md)
- Записная книжка OneNote
- Привязки к другим приложениям Microsoft 365 и Office 365, таким как Планировщик и Power BI

При создании команды из уже существующей группы, ее участники, сайт, почтовый ящик и записная книжка переносятся в Teams. Дополнительные сведения см. на плакате [Группы в Microsoft 365 для ИТ-архитекторов](teams-architecture-solutions-posters.md#groups-in-microsoft-365)

Чтобы настроить и расширить Teams, добавьте сторонние приложения с помощью [задач управления приложениями](deploy-apps-microsoft-teams-landing-page.md). Teams позволяет вам включить в команду или канал пользователей, не являющихся сотрудниками вашей организации, [добавив их в качестве гостей](guest-access.md). Будучи частью Microsoft 365 и Office 365, приложение Teams представляет собой мощную [платформу для разработки](/microsoftteams/platform), которая позволяет создать настоящий центр командной работы для вашей организации.

> [!TIP]
> Для подробного обзора архитектуры Teams посмотрите видео на канале [Teams Platform Academy](https://aka.ms/TeamsPlatformAcademy).

## <a name="managing-teams"></a>Управления Teams

Как администратор вы будете управлять Teams через Центр администрирования Microsoft Teams. Для быстрого ознакомления посмотрите видео "Управление Teams с помощью Центра администрирования Teams" (3:03 минуты).

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yi]

Дополнительные сведения:

- [Управление Teams с ролями администратора](using-admin-roles.md)
- [Управление Teams в Центре администрирования Teams](manage-teams-skypeforbusiness-admin-center.md).
- [Управление Teams при переходе на новую версию Центра администрирования Teams](manage-teams-in-modern-portal.md)
- [Управление функциями Teams в Microsoft 365 или Office 365](enable-features-office-365.md)

Узнать о новых возможностях Teams, а также других продуктов и служб Microsoft 365 или Office 365 в вашей организации можно в [Центре сообщений](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) и из [стратегии развития Teams](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams). Вы будете получать оповещения о новых и обновленных функциях, планируемых изменениях и возможных проблемах, чтобы знать о них и быть готовыми заранее. 

## <a name="upgrade-from-skype-for-business-to-teams"></a>Переход со Skype для бизнеса на Teams
Teams — основной клиент интеллектуальных коммуникаций в Microsoft 365 и Office 365, который со временем заменит Skype для бизнеса Online. Для отслеживания новых функций в Teams см. [стратегию развития Microsoft 365](https://aka.ms/O365Roadmap). В дополнение к функциям сохраняемого чата и обмена сообщениями Teams предлагает комплексные возможности для звонков и собраний с полностью интегрированными средствами голосовой и видеосвязи. Читайте об этом в статье [Teams Is Now a Complete Meeting and Calling Solution](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-is-now-a-complete-meeting-and-calling-solution/ba-p/236042) (Теперь Teams — это полноценное решение для звонков и собраний) в блоге Microsoft Teams.

If you're running Skype for Business and are ready to upgrade to Teams, or if you're running Skype for Business and Teams side-by-side and are ready to fully move to Teams, we have the tools, tips, and guidance to help make your transition successful. To learn more, see [Upgrade to Teams](upgrade-start-here.md).

## <a name="teamwork"></a>Командная работа
Every team is different; there's no one-size-fits-all approach to collaboration. Microsoft 365 and Office 365 are designed to meet the unique needs of every team, empowering people to communicate, collaborate, and achieve more with purpose-built, integrated applications.

При выборе необходимых вам служб и приложений Microsoft 365 или Office 365 подумайте о том, какую работу выполняет ваша организация и какие типы взаимодействия требуются вашим командам. 

- **Teams** — это центр для совместной работы, позволяющий как сотрудникам организации, так и не входящим в нее пользователям, активно общаться и вместе работать над ключевыми проектами в режиме реального времени. Проводите обсуждение именно там, где выполняется задача, будь то коллективное создание документа, проведение собрания или совместная работа в других приложениях и службах. В Teams вы можете проводить неформальные беседы, быстро вносить в проект правки, работать с командой над общими файлами и вместе готовить материалы к сдаче. 

- **Outlook** — используется для совместной работы в привычной среде почтового клиента в более формальном, структурированном формате или когда необходимо более прямое и адресное взаимодействие.

- **SharePoint** — используется для сайтов и порталов, служб интеллектуальной работы с контентом, автоматизации бизнес-процессов и поиска в корпоративной среде. SharePoint хранит все содержимое, используемое для командной работы, и позволяет участникам легко получать или предоставлять к нему доступ. Тесная интеграция с Outlook, Yammer и Teams упрощает работу над контентом в ходе совместных обсуждений.

- **OneDrive for Business** for storing files and sharing them with people that a user invites. Content that a user saves to OneDrive for Business is private until the user shares it with others, making it the best option for storing personal and draft documents that are not intended to be shared or not ready to be shared.

- **Yammer** — позволяет объединить вместе пользователей организации. Организуйте общекорпоративные инициативы, обменивайтесь опытом и создавайте сообщества, посвященные общим темам или сферам деятельности. Выносите идеи на общее открытое обсуждение всей компанией.

- **Приложения Office** — это приложения, которые хорошо знакомы пользователям и с которыми они регулярно работают: Word, Excel, PowerPoint и OneNote. 

## <a name="teams-content-updates"></a>Обновления контента Teams

См. [еженедельный список обновленных статей о Teams](teams-updates.md).

## <a name="teams-known-issues"></a>Известные проблемы Teams

См. [Устранение неполадок Teams](/MicrosoftTeams/troubleshoot/teams)

## <a name="teams-client-release-notes"></a>Заметки о выпуске клиента Teams

См. статью [Новые возможности Teams](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de).