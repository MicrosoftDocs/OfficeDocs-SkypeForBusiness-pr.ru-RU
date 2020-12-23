---
title: Управление Переходом Teams на новый Центр администрирования Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Узнайте, как управлять настройками клиентов и пользователей для Teams во время перехода с Teams в Центре администрирования Microsoft 365 на новый Центр администрирования Teams.
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
ms.openlocfilehash: ee63c3d49a8c4b4bf047f0df3910bec39a4d5541
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790421"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Управление Teams при переходе на новую версию Центра администрирования Microsoft Teams
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>Что такое новый Центр администрирования Microsoft Teams  

Новый интерфейс Центра администрирования обеспечивает единый интерфейс для управления Teams и Skype для бизнеса. Мы будем предоставлять дополнительные функции, концевую информацию и возможность управления настройками Teams на уровне пользователя.

![Снимок экрана: Центр администрирования Microsoft Teams.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Параметры перенесены в новый Центр администрирования Microsoft Teams

В следующей таблице указаны перенесенные разделы интерфейса Teams и показана связь между текущими настройками и политиками на новом портале администрирования.

|Раздел Teams в Центре администрирования Microsoft 365  |Имя параметра (на уровне клиента)  |Политика Центра администрирования Microsoft Teams   |Уровень: клиент или пользователь   |
|---------|---------|---------|---------|
|Общий     |Показывать организационную диаграмму в личном профиле        |  [TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  Клиент       |
|Общий     |Использование Skype для бизнеса для получателей, у которых нет Teams         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиент         |
|Интеграция электронной почты     |Разрешение пользователям отправлять сообщения электронной почты в каналы         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиент         |
|Интеграция электронной почты     |Список "Разрешить отправителей"         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |Клиент         |
|Настраиваемое облачное хранилище     |Box         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиент         |
|Настраиваемое облачное хранилище     |Dropbox        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиент         |
|Настраиваемое облачное хранилище     |Egnyte        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиент         |
|Настраиваемое облачное хранилище     |Google Диск        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиент         |
|Настраиваемое облачное хранилище     |ShareFile        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиент         |
|Параметры по типу пользователя или лицензии     |Отключение и отключение Microsoft Teams для всех пользователей          |Неподготовленные<sup>1</sup>        |         |
|Команды и каналы     |         |Перенаправление на управление группой Azure Active Directory (как и в текущем действии).              |Пользователь         |
|Команды и каналы     |         |Перенаправление на управление группой AAD (как и в текущей ситуации).             |Пользователь          |
|Приложения|Включение новых внешних приложений по умолчанию|Параметры приложений для всей организации|Клиент|
|Приложения|Разрешить внешние приложения|Параметры приложений для всей организации|Клиент|
|Приложения|Разрешить загрузку внешних приложений<sup>2</sup>|[TeamsAppSetupPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|Пользователь|
|Приложения|Приложения по умолчанию<sup>3</sup>|TeamsAppPermissionPolicy|Пользователь|
|Приложения|Внешние<sup>приложения 3</sup>|TeamsAppPermissionPolicy|Пользователь|
|Звонки и собрания     |Разрешить планирование для частных собраний         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Пользователь          |
|Звонки и собрания     |Разрешить встречу в канале Ad-hoc         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Пользователь          |
|Звонки и собрания     |Разрешить планирование для собраний канала         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Пользователь          |
|Звонки и собрания     |Разрешение видео на собраниях         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Пользователь          |
|Звонки и собрания     |Разрешить совместный доступ к экрану на собраниях         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Пользователь          |
|Звонки и собрания     |Разрешить частные вызовы         |[TeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |Пользователь          |
|Обмен сообщениями     |Включить GIPHY, чтобы пользователи могли добавлять GIF-эмотицы в беседы         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Оценка содержимого         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Включить мемы, которые пользователи могут редактировать и добавлять в беседы         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Включить наклейки, которые пользователи могут редактировать и добавлять в беседы         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Разрешить владельцам удалять все сообщения         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Разрешение пользователям изменять собственные сообщения         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Разрешение пользователям удалять собственные сообщения         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Позволяет пользователям общаться в приватном чате         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |

<sup>1</sup> Неподготовлен для гостя. Включением и отключением гостя теперь можно управлять в Центре администрирования Microsoft Teams. Включение и отключение Teams для бизнеса корпоративный, Edu student и Edu faculty в ближайшее время будет отключлено. Для этого нужно назначить лицензии в Центре администрирования Microsoft 365. См. [управление доступом пользователей к Microsoft Teams.](user-access.md)
<br><br>
<sup>Загрузка 2</sup> неогружаемой нагрузки разделяется следующим образом:

- Разрешайте пользователю загрузку приложений, управление которыми на уровне пользователя [в TeamsAppSetupPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)
- Разрешить пользователям в клиенте работать с пользовательскими приложениями, управление которыми можно на уровне клиента в параметрах приложений для всей организации.

В TeamsAppPermissionPolicy на уровне пользователя можно включить и отключить <sup>3</sup> приложения по умолчанию и внешние приложения. Кроме того, приложения могут быть заблокированы на уровне клиента в параметрах приложений для всей организации, что переопределит любые пользовательские и клиентский параметры.

> [!NOTE]
> Вы по-прежнему будете использовать панель мониторинга "Группы" в Центре администрирования Microsoft 365 для настройки, связанной с Teams и каналами. Параметры приложений останутся в области Teams Центра администрирования Microsoft 365 и будут перенесены позже.

## <a name="manage-settings-during-the-migration"></a>Управление настройками во время миграции

Вы можете изменять параметры в Центре администрирования Microsoft 365 и Центре администрирования Skype для бизнеса, пока не завершится перенос раздела для вашего клиента.

В таблице ниже показано, где можно управлять функциями во время миграции.

|Компонент  |Центр администрирования Microsoft Teams                      |Центр администрирования Skype для бизнеса (устаревшая версия)  |Центр администрирования Microsoft 365  |
|---------|:---------:|:---------:|:---------:|
|Политики сообщений, собраний и трансляций Teams     |     X    |         |         |
|Политика обновления Teams     |    X     |         |         |
|Параметры гостя для обмена сообщениями, собраний и голосовой почты     |   X      |         |         |
|Управление жизненным циклом Teams   |    X    |      |       |
|Параметры Teams   |    X    |      |       |
|Параметры внешнего доступа     |    X    |      |       |
|Управление пользователями    |         |         |    X     |
|Аудиоконференции     |    X     |    X     |         |
|Планы звонков     |    X    |    X     |         |
|Телефонная система    |    X    |     X    |         |
|Управление номерами телефонов     |    X    |   X      |         |
|Лицензирование голосовых функций в облаке     |         |         |    X     |
|Автосекретари     |    X    |          |         |
|Очередь звонков     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>Управление настройками после миграции

После переноса этих параметров они будут отключены в Центре администрирования Microsoft 365 и Центре администрирования Skype для бизнеса, а затем управлять ими можно в новом Центре администрирования Microsoft Teams.
