---
title: Сведения о приложениях в Microsoft Teams
ms.reviewer: ''
description: Узнайте о приложениях и решите, какие приложения разрешить в Teams, на основе профиля и бизнес-требований вашей организации.
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 02/10/2021
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b6fd5ef344550cf85420faef1748c34f6e87e88b
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556530"
---
# <a name="about-apps-in-microsoft-teams"></a>О приложениях в Microsoft Teams

Приложения позволяют пользователям находить контент из любимых сервисов и делиться им в Teams. Они позволяют выполнять такие задачи, как закрепление служб вверху канала, автоматизация уведомлений при использовании ботов или открытие доступа к задачам и их назначение. Дополнительные сведения об использовании приложений см. в статье [Обзор приложений для пользователей](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0).

Различные типы приложений, которые пользователи могут использовать в Teams, включают приложения, созданные корпорацией Майкрософт, сертифицированные сторонние приложения и пользовательские приложения, созданные организацией.

## <a name="use-microsoft-provided-apps"></a>Использование приложений, предоставляемых корпорацией Майкрософт

Teams предоставляется с набором встроенных приложений, включая Lists, "Задачи", "Благодарность", "Утверждения" и т. д. Рекомендуется включить избранные приложения Teams, например Планировщик, в первоначальное развертывание Teams. Добавляйте другие приложения по мере внедрения Teams. Некоторые стандартные функции, такие как лента активности, чат, календарь и звонки, доступны по умолчанию и также закреплены для удобства пользователей.

## <a name="use-third-party-apps"></a>Использование сторонних приложений

Помимо приложений, предоставляемых корпорацией Майкрософт, можно использовать сторонние приложения, проверенные Майкрософт. Корпорация Майкрософт сотрудничает с партнерами по разработке Microsoft 365, чтобы предоставлять сведения, необходимые для ускорения принятия решений об использовании приложений Teams. Дополнительные сведения см. в статье [Безопасность приложений Microsoft Teams и их соответствие требованиям](/microsoft-365-app-certification/teams/teams-apps).

## <a name="use-open-source-sample-apps-provided-by-microsoft"></a>Использование примеров приложений с открытым кодом, предоставленных корпорацией Майкрософт

Вы также можете использовать [шаблоны Teams](/microsoftteams/platform/samples/app-templates?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) — готовые к использованию в рабочей среде приложения для Microsoft Teams, которые поддерживаются сообществом, имеют открытый исходный код и доступны в GitHub.

## <a name="create-custom-apps"></a>Создание собственных приложений

Вы можете быстро создать собственные решения с минимальным написанием кода, используя интеграцию Teams с [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions). Кроме того, вы можете создать собственное приложение, соответствующее потребностям вашей организации. Дополнительные сведения см. в статье [Создание приложений для Microsoft Teams](/microsoftteams/platform/overview).  

## <a name="apps-deployment-decisions"></a>Решения по развертыванию приложений

В Teams реализованы прекрасные встроенные возможности совместной работы для вашей организации, и большинство организаций обнаружат, что параметры по умолчанию прекрасно им подходят. Эта статья поможет вам решить, следует ли изменить какие-либо параметры по умолчанию, руководствуясь профилем вашей организации и потребностям бизнеса, а затем поможет вам внести любое изменение. Мы разделили параметры на две группы, начиная с набора основных [изменений, которые вы, скорее всего, внесете](#core-deployment-decisions). Во вторую группу включены [дополнительные параметры](#additional-deployment-decisions), которые можно настроить, исходя из потребностей вашей организации.

## <a name="core-deployment-decisions"></a>Решения по развертыванию основных функций

Ниже перечислены параметры приложений, которые большинство организаций предпочитают изменить (если параметры Teams по умолчанию вам не подходят).

### <a name="app-availability-settings"></a>Настройки доступности приложения

В Teams есть множество приложений, опубликованных Майкрософт и сторонними разработчиками, для вовлечения пользователей, поддержки производительности и интеграции часто используемых бизнес-служб в Teams.
Загрузите приложения из магазина Teams. По умолчанию все приложения, включая пользовательские приложения, которые вы отправляете через [процесс утверждения в Teams Store](/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), активируются для всех пользователей. Например, пользователи могут использовать приложение Планировщик для организации и управления командной работой в Teams.

По умолчанию все предоставляемые Майкрософт и пользовательские приложения и приложения третьих сторон доступны, а вы можете включать или отключать отдельные приложения. Существуют параметры на уровне организации, позволяющие включить или отключить все приложения третьих сторон и (или) пользовательские приложения для вас или всей организации.

| Задайте себе вопрос | Действие |
|--------------|--------|
|Будете ли вы изменять параметры приложений Teams по умолчанию? | Дополнительные сведения о политиках и параметрах, которые можно использовать для управления приложениями в организации, см. в статье [Параметры администратора для приложений в Microsoft Teams](admin-settings.md).|

### <a name="app-permissions-and-other-considerations"></a>Разрешения приложения и другие рекомендации

Приложения получают согласие со стороны пользователей и управляются администратором или IT специалистами в соответствии с политиками. Тем не менее, разрешения приложения и его профиль риска определяются самим приложением.

| Задайте себе вопрос | Действие |
|--------------|--------|
|<br>Каким приложениям я хочу предоставить доступ? Каким приложениями я не хочу предоставлять доступ?  | <ul><li>В статье [Разрешения и рекомендации для приложений Microsoft Teams](app-permissions.md) см. список того, что следует учитывать при предоставлении доступа к приложению, боту, вкладке или соединителю.</li><li>Информацию о том, как сделать приложение доступным для пользователей в вашей организации, см. В разделе [Управление приложениями](manage-apps.md) в центре администрирования Microsoft Teams.</li></ul>|

<!--- TBD: Rewrite this to talk about bots and tabs as a capability of apps. Admins do not govern bots, tabs, etc. Admins only govern apps that contain capabilities such as connectors, bots, etc. This writeup gives an impression that admins manage apps + bots + tabs + connectors, etc.

### Bots for private chats and channels

Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about. Bots allow users to interact with cloud services such as task management, scheduling, and polling in a Teams chat. Teams supports bots in private chats and channels. Administrators can control whether the use of bots is allowed in a Microsoft 365 or Office 365 organization.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow custom bots in my organization?|For more information about adding bots, see [Add bots for private chats and channels in Microsoft Teams](/microsoftteams/platform/bots/what-are-bots). For information about turning custom bots on or off, see [Admin settings for apps in Microsoft Teams](admin-settings.md).|

### Built-in and custom tabs

Owners and team members can add tabs to a channel, private chat, and group chat to help integrate their cloud services. Add tabs to help users access and manage the data they need or use the most. In channels, the Conversations and Files tabs are created by default. In every private chat, the Conversations, Files, Organization, and Activity tabs are created by default. In addition to these built-in tabs, you can design and add custom tabs. To learn about turning Teams apps on or off for your organization, read [Admin settings for apps in Teams](admin-settings.md).

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow custom tabs in my organization?|For more information, see [Use built-in and custom tabs in Teams](built-in-custom-tabs.md).|

### Custom connectors

Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel. With connectors, your Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services in their Teams chats.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow users to create custom connectors?|For more information, see [Use custom connectors in Teams](office-365-custom-connectors.md).|

--->

## <a name="additional-deployment-decisions"></a>Дополнительные решения по развертыванию

Вы можете изменить эти параметры, исходя из потребностей организации и используемой конфигурации.

### <a name="activity-reports"></a>Отчеты о действиях

Чтобы узнать, как пользователи в вашей организации используют Teams, можно использовать отчеты об активности. Например, если некоторые из них еще не используют Команды, они могут не знать, с чего начать, или не понимать, как они могут использовать Команды, чтобы повысить продуктивность и совместную работу. Вы можете использовать отчеты об активности в вашей организации, чтобы определить, где существует приоритетная потребность в обучении и улучшении коммуникации. Чтобы просмотреть отчеты об активности, вы должны обладать правами глобального администратора в Microsoft 365 и Office 365, быть администратором службы Teams или администратором Skype для бизнеса.

| Задайте себе вопрос | Действие |
|--------------|--------|
| <br>Кому требуется просмотр отчетов об активности, и есть ли у них разрешение на просмотр отчетов? |<ul><li>Если вы не хотите передавать пользователю роль администратора, вы можете [назначить ему роль с правами чтения отчетов](teams-activity-reports.md#reports-reader-role).</li><li>См. статьи [Роли и разрешения](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) и [Просмотр и назначение ролей](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) для получения информации и о назначении ролей администратора в Azure Active Directory.</li></ul> |

### <a name="app-templates"></a>Шаблоны приложений

Шаблоны приложений — это готовые использованию в рабочей среде приложения для Майкрософт, которые поддерживаются сообществом, имеют открытый исходный код и доступны в GitHub. Каждое приложение содержит подробные инструкции по его развертыванию и установке для организации и готово к использованию, что позволяет установить и сразу же начать использовать его.

Кроме того, вы получаете полный исходный код, который можно изучить максимально подробно или создать свое ответвление и изменить его для своих конкретных нужд.

| Задайте себе вопрос | Действие |
|--------------|--------|
| Нужно ли мне установить какие-нибудь шаблоны приложений Teams, например, Icebreaker? |Дополнительные сведения см. в статье [Шаблоны приложений для Teams](/microsoftteams/platform/samples/app-templates?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=MicrosoftTeams%2ftoc.json).|
