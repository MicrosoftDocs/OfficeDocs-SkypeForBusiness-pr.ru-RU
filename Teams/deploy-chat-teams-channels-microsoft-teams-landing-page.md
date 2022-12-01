---
title: Чат, команды, каналы и приложения в Microsoft Teams
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.subservice: teams-chat
audience: admin
search.appverid: MET150
description: В этой статье содержатся пошаговые инструкции по настройке параметров Teams для чата, команд, приложений и каналов в Microsoft Teams.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.quickstartteamsadmin
- intro-get-started
- chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3132fdf3e8e04c0527c055435fa95e14d8ca4116
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/30/2022
ms.locfileid: "69199131"
---
# <a name="chat-teams-channels--apps-in-microsoft-teams"></a>Чат, команды, каналы и приложения в Microsoft Teams

Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them. This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change. We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions). The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.

Чтобы начать работу, просмотрите короткое видео о чате, командах и каналах Teams (4:30 мин):

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yj?autoplay=false]

You can use [Advisor for Teams](use-advisor-teams-roll-out.md) to help you roll out Microsoft Teams. Advisor for Teams walks you through your Teams rollout. It assesses your Microsoft 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.

> [!TIP]
> Мы рекомендуем включить избранные приложения, например Планировщик, в начальное развертывание Teams. Добавьте другие [приложения Teams](deploy-apps-microsoft-teams-landing-page.md) по мере внедрения Teams.

 > [!Note]
 > Подробные сведения о функциях Teams на разных платформах см. в статье [Возможности Teams на разных платформах](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="chat-deployment-prerequisites"></a>Необходимые компоненты для развертывания чата

Before you roll out Teams across your organization, take time to confirm that your environment is ready for Teams. Review [Prepare your organization's network for Teams](prepare-network.md) and make any required changes to your environment.

|Задайте себе вопрос|Действие |
|------------|-------|
|Готова ли моя организация к развертыванию Teams?|Чтобы получить ответ на этот вопрос, см.: <ul><li>[Подготовка сети организации к использованию Teams](prepare-network.md)</li><li>[URL-адреса и диапазоны IP-адресов](office-365-urls-ip-address-ranges.md)</li><li>[Планирование использования групп Microsoft 365 при создании команд](plan-office-365-groups.md)</li></ul>|

## <a name="core-deployment-decisions"></a>Основные решения по развертыванию

Ниже перечислены параметры чата, команд и каналов, которые большинство организаций предпочитают изменять (если параметры по умолчанию им не подходят).

### <a name="teams-administrators"></a>Администраторы Teams

Teams provides a set of custom administrator roles that can be used to manage Teams for your organization. The roles provide various capabilities to administrators.

| Задайте себе вопрос | Действие |
|--------------|--------|
|Кто будет назначен на роль администратора коммуникаций Teams?|Чтобы узнать больше о ролях администратора Teams, см.статью [Использования ролей администратора в Microsoft Teams для управления Teams](using-admin-roles.md).|
|Кому будет назначена роль инженера службы поддержки Teams Communications?|Дополнительные сведения о назначении ролей администратора см. в статье [Назначение ролей с правами администратора и без для пользователей Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).|
|Кто будет назначен на роль специалиста поддержки по коммуникациям Teams?||

### <a name="teams-owners-and-members"></a>Владельцы и участники Teams

In addition to administrator roles, Teams lets you assign owner and member user roles, and selectively give them moderator capabilities (if moderation has been set up) to control who can perform certain actions within a channel. Moderation allows you to control who can start new posts in a channel, add and remove team members as moderators, and control whether team members can reply to existing channel messages.

|Задайте себе вопрос|Действие |
|------------|-------|
|Кому следует назначить каждую роль? | Сравнение возможностей каждой роли см. в статье [Назначение владельцев, модераторов и участников команд в Microsoft Teams](assign-roles-permissions.md).
|Как назначить роль пользователя? | Сведения о том, как назначить или изменить роль, см. в статье [Назначение роли пользователя](assign-roles-permissions.md).
|Нужно ли управлять тем, кто может публиковать сообщения и отвечать на них в канале? | Сведения о настройке модерации см. в статье [Настройка модерации канала в Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="messaging-policies"></a>Политики обмена сообщениями

Messaging policies control which chat and channel messaging features are available to users in Teams. For example, who can edit and delete sent messages, who can use chat, who can use memes in conversations, and more. By default, users are assigned the global messaging policy and all features are **On**. You can use the default global policy or create one or more custom messaging policies for people in your organization.

|Задайте себе вопрос|Действие |
|------------|-------|
|Нужно ли настраивать глобальную политику обмена сообщениями?|Сведения об использовании Центра администрирования Microsoft Teams для изменения глобальной политики обмена сообщениями или добавления новой политики см. в статье [Управление политиками обмена сообщениями в Teams](messaging-policies-in-teams.md).|
|Потребуется ли мне несколько политик обмена сообщениями?|Чтобы создать и назначить политику обмена сообщениями в оболочке PowerShell, см. статью [Пример сценария PowerShell — Создание и назначение политики обмена сообщениями](scripts/powershell-script-teams-messaging-policy-edu.md).|
|Как определить, какая политика собрания применяется к тем или иным группам пользователей?|Дополнительные сведения о командлетах CsTeamsMessagingPolicy см. в статье [Настройка - CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy).|

### <a name="external-access"></a>Внешний доступ

External access (federation) lets your users communicate with people outside of your organization via chat. By turning this on and adding domains to the allowed list, your users can communicate with users in other domains and organizations. External access is turned on by default.

|Задайте себе вопрос|Действие |
|------------|-------|
|<ul><li>Нужно ли мне отключить внешние собрания и чаты для моей организации?</li><li>Если эта возможность включена, смогу ли я указать, какие домены могут подключиться к моей организации?</li></ul> |<br>Чтобы включить или отключить внешние собрания и чат, см. статью [Управление внешними собраниями и чатом](manage-external-access.md).|

### <a name="guest-access"></a>Гостевой доступ

Guest access in Teams lets individuals outside your organization access teams and channels. You can use the guest access settings to control which features guests can or can't use. Guest access is turned on by default. To learn more, see [Guest access in Teams](./guest-access.md).

> [!NOTE]
> Дополнительные сведения о внешнем доступе и гостевом доступе см. в статье [Общение с пользователями из других организаций в Microsoft Teams](communicate-with-users-from-other-organizations.md).

|Задайте себе вопрос|Действие |
|------------|-------|
|Нужно ли мне отключить гостевой доступ для моей организации?|Чтобы включить или выключить функцию гостевого доступа, ознакомьтесь со статьей [Включение и отключение гостевого доступа в Teams](set-up-guests.md).|
|Если эта возможность включена, нужно ли будет настраивать список возможностей, доступных для гостей моей организации?|Чтобы настроить доступность функций для гостевого доступа, см. статью [Разрешение гостевого доступа в Teams](teams-dependencies.md).|

### <a name="private-channels"></a>Частные каналы

Частные каналы позволяют подмножеству участников команды совместно работать в закрытом пространстве, которое не могут видеть и к которому не имеют доступа остальные участники команды. Любых пользователей, в том числе гостей, можно добавлять в закрытый канал в качестве членов, если эти пользователи уже являются членами команды.

|Задайте себе вопрос|Действие |
|------------|-------|
|Разрешить ли владельцам и участникам команды создавать частные каналы?|Чтобы настроить политику частных каналов для организации, ознакомьтесь со статьей [Управление политиками каналов в Microsoft Teams](teams-policies.md)|

### <a name="shared-channels"></a>Общие каналы

Общие каналы позволяют добавлять в канал пользователей, которые не являются членами команды. Это относится и к пользователям за пределами вашей организации. Общие каналы имеют преимущества перед гостевым доступом, поскольку пользователям за пределами вашей организации не нужна гостевая учетная запись в вашем каталоге.

|Задайте себе вопрос|Действие |
|------------|-------|
|Когда общие каналы следует предпочесть гостевому доступу?|См статью [Общие каналы в Microsoft Teams](shared-channels.md).|
|<ul><li>Нужно ли мне разрешить владельцам команд создавать общие каналы?</li><li>Нужно ли мне разрешить владельцам команд делиться каналами с пользователями за пределами организации?</li><li>Нужно ли мне разрешить пользователям участвовать в общих каналах, которые находятся за пределами организации?</li></ul> |<br>Чтобы установить политику общих каналов для вашей организации, ознакомьтесь со статьей [Управление политиками каналов в Microsoft Teams](teams-policies.md).|

### <a name="teams-settings"></a>Параметры Teams

Teams settings let you set up your teams for features such as email integration, cloud storage options, organization tab, meeting room device setup, and search scope. When you make changes to these settings, they apply to all the teams in your organization. To learn more, see [Teams settings](enable-features-office-365.md#teams-settings).

|Задайте себе вопрос|Действие |
|------------|-------|
|Нужно ли настраивать параметры Teams для моей организации? | Сведения о параметрах Teams и их настройки см. в статье [Параметры Teams](enable-features-office-365.md#teams-settings).|

### <a name="teams-clients"></a>Клиенты Teams

Teams supports a number of clients from web to desktop to mobile, and the default configuration lets users choose whichever clients they want. To learn more, see [Get clients for Teams](get-clients.md).

|Задайте себе вопрос|Действие |
|------------|-------|
|Нужно ли настраивать доступность клиентов Teams для моей организации?|Ознакомьтесь со статьей [Аппаратные требования для приложения Teams](hardware-requirements-for-the-teams-app.md) |
|Нужно ли настраивать параметры клиента Teams для моей организации?|Узнайте, как [установить Teams с помощью MSI](msi-deployment.md).|

### <a name="teams-usage-reporting"></a>Отчеты об использовании Teams

The Global Admin, Teams Service Admin, and Reports Readers roles can view Teams usage reports. To learn more, see the [Microsoft 365 usage analytics](/microsoft-365/admin/usage-analytics/usage-analytics).

|Задайте себе вопрос|Действие |
|------------|-------|
|<br> Кому требуется просмотр отчетов об активности в Teams, и есть ли у них роль, дающая право на просмотр отчетов? |<ul><li>Если пользователь не являетесь администратором [необходимо назначить роль пользователя с правами чтения отчетов](teams-activity-reports.md#reports-reader-role).</li><li>См. статьи [Роли и разрешения](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) и [Просмотр и назначение ролей](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) для получения информации о назначении ролей администратора в Azure Active Directory.|

### <a name="teams-default-apps"></a>Приложения Teams по умолчанию

Teams provides a number of first-party (Microsoft provided) and third-party apps to engage users, support productivity, and integrate commonly used business services into Teams. Get apps from the Teams Store. Apps are turned on by default in Teams.

Дополнительные сведения о выпуске приложений и управлении ими в Teams см. в нашем подробном руководстве по [управлению приложениями](deploy-apps-microsoft-teams-landing-page.md) .

## <a name="additional-deployment-decisions"></a>Дополнительные решения по развертыванию

Вы можете изменить эти параметры, исходя из потребностей вашей организации и используемой конфигурации.

### <a name="teams-licensing"></a>Лицензирование Teams

Teams предоставляется в составе многих лицензий Microsoft 365.

|Задайте себе вопрос|Действие |
|------------|-------|
|У пользователей есть лицензии, которые нужны для использования всех функций Teams, который мне нужно развернуть? | Чтобы узнать о лицензионных требованиях, прочтите [описание службы Microsoft Teams](/office365/servicedescriptions/teams-service-description).|

### <a name="exchange-and-sharepoint-interoperability"></a>Взаимодействие между Exchange и SharePoint

For the full Teams experience, every user should be enabled for Exchange, SharePoint, and Microsoft 365 group creation. The following articles outline information related to Exchange mailboxes hosted in various environments, how Exchange and Teams interact, and similar considerations for SharePoint and OneDrive.

|Задайте себе вопрос|Действие |
|------------|-------|
| Можно ли выполнять развертывание необходимых функций Teams с текущими развертываниями Exchange и SharePoint? |Дополнительные сведения об Exchange и SharePoint в Teams см.:<ul><li> [Взаимодействие Exchange и Teams](exchange-teams-interact.md)</li><li>[Взаимодействие SharePoint Online и OneDrive с Teams](sharepoint-onedrive-interact.md)|

### <a name="teams-limits-and-specifications"></a>Ограничения и спецификации Teams

При планировании корпоративного развертывания Teams вам следует учитывать все важные ограничения и спецификации, такие как максимальное количество участников команды, максимальное количество команд, которые пользователь может создавать и т. д.

|Задайте себе вопрос|Действие |
|------------|-------|
| С какими ограничениями я скорее всего столкнусь при развертывании Teams? | Дополнительные сведения см. в статье [Ограничения и спецификации для Teams](limits-specifications-teams.md). |

### <a name="urls-and-ports"></a>URL-адреса и порты

Organizations that maintain fine-grained control of their internet traffic should read [URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges) for an up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams. Microsoft is continuously improving the Microsoft 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time. We recommend that you subscribe via RSS to receive notifications when this information is updated or changed. At a minimum, make sure you've opened the ports listed above in [Chat deployment prerequisites](#chat-deployment-prerequisites).

|Задайте себе вопрос|Действие |
|------------|-------|
| Потребуются ли правила доступа к сети Интернет, чтобы пользователи могли использовать Teams, или достаточно открыть минимальное обязательное количество портов? | Дополнительные сведения см. в статье [URL-адреса и диапазоны IP-адресов](office-365-urls-ip-address-ranges.md).|

### <a name="governance-naming-conventions-who-can-create-teams"></a>Управление (соглашения об именовании, кто имеет право на создание команд)

Your organization might require that you implement controls on how teams are named and classified, who can create teams, and team expiration, retention, and archiving. This is called governance. You can use Azure Active Directory (Azure AD) to configure each of these areas.

| Задайте себе вопрос | Действие |
|--------------|--------|
|Мне необходимо будет реализовать элементы управления, чтобы определять, кто может создавать команды?| Ознакомьтесь со статьей [Планирование управления в SharePoint](plan-teams-governance.md).|
|Мне необходимо будет реализовать элементы управления, чтобы определять, как будут присваиваться имена для команд?|Ознакомьтесь со статьей [Использование политики именования для групп Microsoft 365 в Azure AD](/azure/active-directory/users-groups-roles/groups-naming-policy).|

### <a name="teams-application-policy-side-rail-control"></a>Политика приложений Teams (стороннее управление)

A pinned app shows up in the side rail in Teams. By creating Teams application policies, you can preconfigure sets of pinned Teams apps to personalize Teams for select groups of users. By default, the **Allow external apps in Microsoft Teams** setting is turned on.

| Задайте себе вопрос | Действие |
|--------------|--------|
|Необходимо ли мне создать предопределенные наборы закрепленных приложений Teams? | Ознакомьтесь со статьей [Параметры администратора для приложений в Teams](admin-settings.md)|
|Как я смогу решить, какие группы будут получать эти группы приложений?|Ознакомьтесь со статьей [Разрешения и рекомендации для приложений Microsoft Teams](app-permissions.md)|

### <a name="archiving-and-compliance"></a>Архивирование и соответствие требованиям

Your organization might require that you implement controls on how teams are archived and the types of data that are held in certain types of teams. Read [Overview of security and compliance in Teams](security-compliance-overview.md) to learn which Teams settings are turned on by default.

| Задайте себе вопрос | Действие |
|--------------|--------|
|Мне будет необходимо настроить сохранение команды?|Чтобы настроить политики хранения, см. статью [Настройка политик хранения Teams](retention-policies.md).|
|Мне будет необходимо настроить архивацию группы?|Процесс архивации или восстановления команды см. в статье [Архивация или восстановление команды](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).|
|Мне необходимо настроить дополнительные параметры соответствия требованиям?|Дополнительные сведения о безопасности и соответствия требованиям см. в статье [Общие сведения о безопасности и соответствии требованиям в Teams](security-compliance-overview.md).|

### <a name="conditional-access"></a>Условный доступ

Teams relies heavily on Exchange and SharePoint for core productivity scenarios, including meetings, calendars, interop chats, and file sharing. Conditional access policies that are set for these cloud apps apply to Teams when a user signs in directly to Teams, on any client. Conditional access policies that are set for the Teams cloud app control aspects such as whether users can access Teams services from certain networks.

| Задайте себе вопрос | Действие |
|--------------|--------|
|<br>Мне необходимо настраивать условный доступ для Teams?|<ul><li>Чтобы понять, как работают политики доступа, см. статью [Как работают политики условного доступа в Teams?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)</li><li>Информацию о настройке многофакторной проверки подлинности для Teams см.:<ul><li>[Краткое руководство: Необходимость многофакторной проверки подлинности для конкретных приложений с помощью условного доступа Azure Active Directory](/azure/active-directory/conditional-access/app-based-mfa)</li><li>[Настройки условного доступа с помощью Azure Active Directory](/azure/active-directory/conditional-access/technical-reference)</li></ul></ul>|

### <a name="education-edu"></a>Образование

ИТ-специалисты, работающие в образовательных учреждениях, могут воспользоваться преимуществами версии Teams для образовательных учреждений, который поставляется с широким набором возможностей, которые были специально заточены под сценарии для учащихся, преподавателей и широкого бизнеса.

| Задайте себе вопрос | Действие |
|--------------|--------|
|Буду ли я использовать шаблоны Teams для учебных заведений? |Дополнительные сведения о Teams для образовательных учреждений см. в статье [Вопросы и ответы для администраторов по управлению Microsoft Education](plan-teams-governance-edu.md).|
|Будет ли развернута заданная областью поиска?|Сведения о настройке Teams для учебных заведений см. в статье [Краткое руководство: администраторы Teams для образовательных учреждений](teams-quick-start-edu.yml).|
|Будет ли интегрирована в Teams служба School Data Sync для подготовки учетных записей пользователей?|[Ресурсы Teams для образовательных учреждений (администраторы)](resources-teams-edu.md)|

### <a name="government---gcc-considerations"></a>Государственных организаций - Советы и рекомендации в отношении GCC

Использование Office 365 для государственных организаций — GCC (облако сообщества для государственных организаций) отвечает требованиям ИТ-специалистов, выполняющих развертывания Office 365 в федеральных, региональных, местных, племенных или территориальных государственных организациях США или других организациях, обрабатывающих данные, регулируемые государственными нормами и требованиями.

| Задайте себе вопрос | Действие |
|--------------|--------|
| Потребуется ли развертывать Teams в среде Office 365 для государственных организаций — GCC? | Рекомендации по развертыванию см. в статье [План для развертывания Office 365 для государственных организаций — GCC](plan-for-government-gcc.md).|

## <a name="next-steps"></a>Дальнейшие действия

- [Внедрение](adopt-microsoft-teams-landing-page.md) чата, команд, каналов и приложений.
- Включите рекомендуемые приложения - такие как Планировщик – в первоначальное развёртывание Teams. Добавьте другое [приложение Teams](deploy-apps-microsoft-teams-landing-page.md) при внедрении Teams.
- [Развертывание собраний и конференций](deploy-meetings-microsoft-teams-landing-page.md)
- [Развертывание облачной системы голосовой связи](cloud-voice-landing-page.md)
