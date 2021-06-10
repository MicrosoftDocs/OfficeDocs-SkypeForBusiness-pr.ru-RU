---
title: Управление Teams переходом на новую Teams администрирования
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Узнайте, как управлять настройками клиента и пользователей Teams во время перехода Teams в Центре администрирования Microsoft 365 на новый Teams администрирования.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- ms.teamsadmincenter.dashboard.helparticle.manageteamsnewadmincenter
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: 875db7be64e23b32f5f758f9f5a701199c068528
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100905"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Управление Teams при переходе на новую версию Центра администрирования Microsoft Teams
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>Что нового в Центре Microsoft Teams администрирования  

Новый интерфейс Центра администрирования обеспечивает единый интерфейс для управления Teams и Skype для бизнеса. Мы будем предоставлять дополнительные функции, готовые сведения и возможность Teams параметров на уровне пользователя.

![Снимок экрана: Microsoft Teams администрирования.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Параметры новый Центр администрирования Microsoft Teams учетной Microsoft Teams

В таблице ниже указаны разделы перенесенного интерфейса Teams и показана связь между текущими настройками и политиками на новом портале администрирования.

|Раздел раздела Teams в Microsoft 365 центре администрирования  |Имя параметра (уровень клиента)  |Microsoft Teams политики Центра администрирования   |Уровень: клиент или пользователь   |
|---------|---------|---------|---------|
|Общие     |Показать организационную диаграмму в личном профиле        |  [TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  Арендатор       |
|Общие     |Используйте Skype для бизнеса для получателей, у которых нет Teams         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Арендатор         |
|Интеграция электронной почты     |Разрешение пользователям отправлять сообщения электронной почты в каналы         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Арендатор         |
|Интеграция электронной почты     |Список "Разрешить отправителей"         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |Арендатор         |
|Настраиваемое облачное хранилище     |Коробка         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Арендатор         |
|Настраиваемое облачное хранилище     |Dropbox        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Арендатор         |
|Настраиваемое облачное хранилище     |Egnyte        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Арендатор         |
|Настраиваемое облачное хранилище     |Google Диск        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Арендатор         |
|Настраиваемое облачное хранилище     |Sharefile        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Арендатор         |
|Параметры по типу пользователя или лицензии     |Отключение Microsoft Teams для всех пользователей          |Неподготовленные<sup>1</sup>        |         |
|Команды и каналы     |         |Перенаправляет на Azure Active Directory групп (то же, что и в текущий момент).              |Пользователь         |
|Команды и каналы     |         |Перенаправляет на управление группой AAD (так же, как в текущем).             |Пользователь          |
|Приложения|Включение новых внешних приложений по умолчанию|Параметры приложений для всей организации|Арендатор|
|Приложения|Разрешить внешние приложения|Параметры приложений для всей организации|Арендатор|
|Приложения|Разрешить загрузку внешних приложений<sup>2</sup>|[TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|Пользователь|
|Приложения|Приложения по умолчанию<sup>3</sup>|TeamsAppPermissionPolicy|Пользователь|
|Приложения|Внешние приложения<sup>3</sup>|TeamsAppPermissionPolicy|Пользователь|
|Звонки и собрания     |Разрешить планирование для частных собраний         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Пользователь          |
|Звонки и собрания     |Разрешить встречу в Ad-hoc-канале         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Пользователь          |
|Звонки и собрания     |Разрешить планирование для собраний канала         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Пользователь          |
|Звонки и собрания     |Разрешение видео на собраниях         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Пользователь          |
|Звонки и собрания     |Разрешение общего доступа к экрану на собраниях         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Пользователь          |
|Звонки и собрания     |Разрешить частные вызовы         |[TeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |Пользователь          |
|Обмен сообщениями     |Включить Giphy, чтобы пользователи могли добавлять GIF-эмотики в беседы         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Оценка содержимого         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Включить мемы, которые пользователи могут редактировать и добавлять в беседы         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Включить наклейки, которые пользователи могут редактировать и добавлять в беседы         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Разрешить владельцам удалять все сообщения         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Разрешение пользователям изменять собственные сообщения         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Разрешение пользователям удалять собственные сообщения         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Позволяет пользователям общаться в приватном чате         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |

<sup>1</sup> Неподготовлен для гостей. Включением и отключением гостя теперь можно управлять в центре Microsoft Teams администрирования. Включение и отключение Teams для бизнеса Enterprise, студентов и преподавателей Edu скоро будет отключать. Для этого следует назначить лицензии в центре Microsoft 365 администрирования. См. [управление доступом пользователей к Microsoft Teams.](user-access.md)
<br><br>
<sup>2 Загрузка</sup> на стороне разделяется следующим образом:

- Разрешить пользователю загрузку приложений, управление которыми можно управлять на уровне [пользователя в TeamsAppSetupPolicy.](/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)
- Разрешить пользователям в клиенте работать с пользовательскими приложениями, управление которыми можно управлять на уровне клиента в настройках приложений для всей организации.

<sup>3</sup> Приложения по умолчанию и внешние приложения можно включить и отключить на уровне пользователя в TeamsAppPermissionPolicy. Кроме того, приложения могут быть заблокированы на уровне клиента в настройках приложений для всей организации, что переопределит любые пользовательские и клиентский параметры.

> [!NOTE]
> Вы по-прежнему будете использовать панель мониторинга "Группы" в Центре Microsoft 365 для настройки, связанной с Teams и каналами. Параметры для приложений останутся в области Teams центра администрирования Microsoft 365 и будут перенесены позже.

## <a name="manage-settings-during-the-migration"></a>Управление настройками во время миграции

Вы можете изменять параметры в центре администрирования Microsoft 365 и центре администрирования Skype для бизнеса до завершения миграции раздела для вашего клиента.

В таблице ниже показано, где можно управлять функциями во время миграции.

|Компонент  |Microsoft Teams центре администрирования                      |Skype для бизнеса администрирования (устаревшая версия)  |Microsoft 365 центре администрирования  |
|---------|:---------:|:---------:|:---------:|
|Teams Политики сообщений, собраний и трансляций     |     X    |         |         |
|Teams Политика обновления     |    X     |         |         |
|Параметры гостя для обмена сообщениями, собраний и голосовой почты     |   X      |         |         |
|Teams Управление жизненным циклом   |    X    |      |       |
|Teams Параметры   |    X    |      |       |
|Параметры внешнего доступа     |    X    |      |       |
|Управление пользователями    |         |         |    X     |
|Аудиоконференции     |    X     |    X     |         |
|Планы звонков     |    X    |    X     |         |
|Телефонная система    |    X    |     X    |         |
|Телефон управления номерами     |    X    |   X      |         |
|Лицензирование голосовых функций в облаке     |         |         |    X     |
|Автосекретари     |    X    |          |         |
|Очередь звонков     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>Управление настройками после миграции

После переноса этих параметров они отключались в Центре администрирования Microsoft 365 и центре администрирования Skype для бизнеса, а затем управлять ими можно в новом центре Microsoft Teams администрирования.