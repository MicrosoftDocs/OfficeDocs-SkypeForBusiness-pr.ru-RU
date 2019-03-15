---
title: Управление функциями Microsoft Teams в организации Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/29/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: Узнайте, как включать и отключать приложения Microsoft Teams в организации Office 365, в том числе вкладки, соединители, боты и любое их сочетание.
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a7712caa826804d26fd2e3527183128ce78520c3
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2019
ms.locfileid: "30460238"
---
# <a name="manage-microsoft-teams-features-in-your-office-365-organization"></a>Управление функциями Microsoft Teams в организации Office 365

В скором времени все настройки Teams будут перенесены в новый Центр администрирования Microsoft Teams. Единственным компонентом Teams, который управляется в Центре администрирования Microsoft 365, остаются "Приложения". 

Если не указано иное, по умолчанию параметры имеют значение **Вкл**.

## <a name="tenant-wide-settings"></a>Параметры на уровне клиента 

Вы можете включать и отключать приложения для Teams в разделе **Параметры на уровне клиента** в Центре администрирования Microsoft 365. 

Чтобы изменить **Параметры на уровне клиента** для Teams, войдите в Центр администрирования Microsoft 365 и выберите **Параметры** > **Службы и надстройки** > **Microsoft Teams**. Если вы вошли с правами администратора Office 365, воспользуйтесь ссылкой: 

https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

### <a name="apps"></a>Приложения

Apps are tabs, connectors, bots, or any combination of these three, provided by Teams (first-party apps, also known as default apps) or by a third-party (also known as external apps). Under **Apps**, you can enable and disable default apps and configure settings to control external apps.  

#### <a name="default-apps"></a>Приложения по умолчанию

These apps, such as Planner, Praise, and Weather, are provided by Teams. To turn on an app, select the check box for that app. To turn off an app, clear the check box. 

![Снимок экрана раздела "Приложения по умолчанию".](media/teams-manage-features-in-office365-image1.png "Снимок экрана раздела \"Приложения по умолчанию\"")

#### <a name="external-apps"></a>Внешние приложения

These apps are provided by third parties. You can configure the following settings for external apps.

![Снимок экрана раздела "Внешние приложения".](media/teams-manage-features-in-office365-image2.png "Снимок экрана раздела \"Внешние приложения\" с включаемыми и отключаемыми параметрами")

- **Разрешить внешние приложения в Microsoft Teams**. При включении этого параметра пользователи могут добавлять внешние приложения, доступные вашей организации. 

- **Allow sideloading of external apps**: If you want to turn on some external apps and turn off others , turn off this setting, and then in the list of external apps, turn off the apps that you don't want users to access. When this setting is turned on, team owners and members who are granted permission can sideload apps to Teams. 

- **Enable new external apps by default**: When this setting is turned on, users can activate new apps as soon as they're added to the Teams app catalog. Turn off this setting if you want to control new apps. Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on new apps. 

Дополнительные сведения: [Параметры администратора для приложений в Teams](admin-settings.md). 

## <a name="teams-org-wide-settings"></a>Параметры Teams на уровне организации

Вы можете управлять параметрами пользователя для всей организации в Центре администрирования Microsoft Teams. Чтобы изменить параметры для всей организации, перейдите в Центр администрирования Microsoft Teams и выберите **Параметры для всей организации**. Вы можете настроить перечисленные ниже параметры.

### <a name="external-access"></a>Внешний доступ

**Внешний доступ** позволяет пользователям Teams и Skype для бизнеса взаимодействовать с внешними контактами за пределами вашей организации. Сведения о настройке внешнего доступа см. в статье об [активации чата и взаимодействия с пользователями Teams из другой организации](let-your-teams-users-communicate-with-other-people.md).

### <a name="guest-access"></a>Гостевой доступ

**Гостевой доступ** в Microsoft Teams позволяет командам в вашей организации взаимодействовать с людьми, которые в нее не входят, предоставляя им доступ к командам и каналам. Любой пользователь с корпоративной или потребительской учетной записью Outlook, Gmail или других служб может участвовать в Teams в качестве гостя с полным доступом к командным чатам, собраниям и файлам. Дополнительные сведения см. в разделе [Гостевой доступ в Microsoft Teams](guest-access.md).

### <a name="teams-settings"></a>Параметры Teams

**Параметры Teams** позволяют интегрировать электронную почту, выбрать облачные хранилища, организовать взаимодействие со Skype для бизнеса и настроить ваши устройства.

#### <a name="email-integration"></a>Интеграция с электронной почтой

Включите эту функцию, чтобы пользователи могли отправлять письма на электронный адрес канала в Teams. Это будет доступно для любого канала принадлежащей им команды. Кроме того, пользователи могут отправлять электронные письма в любые каналы команд, участникам которых разрешено добавлять соединители. Чтобы включить интеграцию электронной почты, установите для параметра **Разрешить пользователям отправлять письма на электронный адрес канала** значение **Вкл**. 

#### <a name="files"></a>Файлы

Здесь вы можете включать и отключать параметры обмена файлами и облачного файлового хранилища. 

Пользователи могут загружать и отправлять друг другу файлы из облачных служб хранения в каналах и чатах Teams. В качестве облачного хранилища Teams сейчас поддерживает ShareFile, Dropbox, Box и Google Диск. Установите переключатель напротив поставщиков услуг облачного хранения, которые нужно использовать в вашей организации.

#### <a name="organization"></a>Организация

Здесь вы можете включить вкладку **Организация**, где отображается подробная организационная диаграмма компании пользователя. Дополнительные сведения см. в разделе [Использование вкладки "Организация" в Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).

#### <a name="devices"></a>Устройства

Эти параметры управляют работой учетных записей ресурсов на устройствах Surface Hub, используемых в собраниях Microsoft Teams. Они позволяют настраивать требования проверки подлинности и ПИН-коды доступа к контенту, а также включать учетные записи ресурсов Surface Hub для отправки сообщений.

- **Требовать дополнительную форму проверки подлинности для доступа к содержимому собрания** — используется для выбора уровня доступа, который получат пользователи при вводе ПИН-кода контента.
- **Задать ПИН-код контента** — требовать, чтобы пользователи вводили этот ПИН-код, для предотвращения несанкционированного доступа к документам. Это позволяет не допускать неправомочных пользователей к участию в собраниях и просмотру их материалов.
- **Разрешить учетным записям ресурсов отправлять сообщения** — установите для этого параметра значение **Вкл**, чтобы разрешить отправку сообщений из учетной записи ресурса Surface Hub.

#### <a name="search"></a>Поиск

Microsoft Teams позволяет организациям назначать политику адресных книг Exchange для поиска только в определенных областях каталога: таким образом они могут задавать пользователям внутри компании виртуальные границы для поиска и взаимодействия друг с другом. Поиск в области каталога будет целесообразен, к примеру, в следующих ситуациях:

- В рамках клиента организации существует множество компаний, которые должны быть независимы друг от друга. 
- В учебном заведении требуется ограничить возможности общения преподавателей с учащимися в чатах. 

Установите параметр в значение **Вкл**, чтобы активировать функции поиска в области каталога.

### <a name="teams-upgrade"></a>Переход на Teams

Эти параметры можно использовать для настройки перехода пользователей со Skype для бизнеса на Microsoft Teams. 

#### <a name="coexistence-mode"></a>Режим сосуществования
Можно указать следующие режимы сосуществования: **Только Teams**, **Острова** (сосуществование Teams и Skype для бизнеса) или **Только Skype для бизнеса**. Выбранный режим определяет маршрутизацию входящих звонков и чатов, а также пользовательское приложение, применяемое для инициации чатов и звонков или для планирования собраний. Дополнительные сведения см. в статье о [сосуществовании и взаимодействии Microsoft Teams и Skype для бизнеса](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

#### <a name="app-preferences"></a>Настройки приложений

Здесь вы можете выбрать приложение, в котором пользователи будут присоединяться к собраниям Skype для бизнеса (Skype для бизнеса или [приложение "Собрания Скайпа"](https://support.office.com/ru-RU/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). Этот параметр не зависит от настройки режима сосуществования.

## <a name="how-can-i-tell-which-features-are-available"></a>Как узнать, какие функции доступны?

Сведения о новых функциях Teams см. на странице [Стратегия развития Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams). Для получения дополнительных сведений о новых и планируемых функциях Teams см. страницу [Новые возможности](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) и [блог Tech Community, посвященный Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531). 

## <a name="more-information"></a>Дополнительные сведения

Сведения о том, какие роли могут выполнять функции администратора, см. в статье [Управление Microsoft Teams с ролями администратора](using-admin-roles.md).
