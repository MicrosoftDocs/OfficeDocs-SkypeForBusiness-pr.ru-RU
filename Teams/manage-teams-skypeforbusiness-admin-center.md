---
title: Управление переходом команд в новой версии центра администрирования Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Сведения о том, как управлять параметрами на уровне клиента и пользователями для Teams во время перехода с Teams в центре администрирования Microsoft 365 в новый центр администрирования Teams.
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
ms.openlocfilehash: dd1a94ab587b21fce5a455300826632ffd508042
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581540"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Управление Teams при переходе на новую версию Центра администрирования Microsoft Teams
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>Общие сведения о новом центре администрирования Microsoft Teams  

Новые возможности центра администрирования предоставляют единый интерфейс для управления группами и Skype для бизнеса. Мы предлагаем дополнительные функции, сквозное представление и возможность управлять параметрами групп на уровне пользователя.

![Снимок экрана: центр администрирования Microsoft Teams.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Параметры, перенесенные в новый центр администрирования Microsoft Teams

В приведенной ниже таблице указаны разделы, которые были перенесены, и показана связь между текущими параметрами и политиками на новом портале администрирования.

|Раздел "Teams" в центре администрирования Microsoft 365  |Имя параметра (уровень клиента)  |Политика центра администрирования Microsoft Teams   |Level (уровень): клиент или пользователь   |
|---------|---------|---------|---------|
|Общий     |Показать организационную диаграмму в личном профиле        |  [TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  Клиента       |
|Общий     |Использование Skype для бизнеса для получателей, не имеющих групп         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиента         |
|Интеграция электронной почты     |Разрешение пользователям отправлять сообщения электронной почты по каналам         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиента         |
|Интеграция электронной почты     |Список разрешенных отправителей         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |Клиента         |
|Настраиваемое облачное хранилище     |Полем         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиента         |
|Настраиваемое облачное хранилище     |Данных        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиента         |
|Настраиваемое облачное хранилище     |Egnyte (ожидается в ближайшее время)        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиента         |
|Настраиваемое облачное хранилище     |Google диск        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиента         |
|Настраиваемое облачное хранилище     |ShareFile        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиента         |
|Параметры по типу пользователя и лицензии     |Включение и отключение Microsoft Teams для всех пользователей          |Устаревший<sup>1</sup>        |         |
|Группы и каналы     |         |Перенаправляет Управление группами Azure Active Directory (то же, что и текущий интерфейс).              |Пользователь         |
|Группы и каналы     |         |Перенаправление на управление группами AAD (то же, что и текущий интерфейс).             |Пользователь          |
|Приложения|Включение новых внешних приложений по умолчанию|Параметры приложения в масштабе Организации|Клиента|
|Приложения|Разрешить внешние приложения|Параметры приложения в масштабе Организации|Клиента|
|Приложения|Разрешение неопубликованных приложений для внешних приложений<sup>2</sup>|[TeamsAppSetupPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|Пользователь|
|Приложения|Приложения по умолчанию<sup>3</sup>|TeamsAppPermissionPolicy|Пользователь|
|Приложения|Внешние приложения<sup>3</sup>|TeamsAppPermissionPolicy|Пользователь|
|Звонки и собрания     |Разрешить планирование для частных собраний         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Пользователь          |
|Звонки и собрания     |Разрешить рекламный канал обсудим         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Пользователь          |
|Звонки и собрания     |Разрешить планирование для собраний канала         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Пользователь          |
|Звонки и собрания     |Разрешение видеороликов в собраниях         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Пользователь          |
|Звонки и собрания     |Разрешение демонстрации экрана в собраниях         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Пользователь          |
|Звонки и собрания     |Разрешить частный Звонок         |[TeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |Пользователь          |
|Обмен сообщениями     |Включение GIF, чтобы пользователи могли добавлять в беседы GIF-файлы         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Рейтинг контента         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Включение мемов, которые пользователи могут редактировать и добавлять в беседы         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Включение поддержки наклеек, которые пользователи могут редактировать и добавлять в беседы         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Разрешить владельцам удалять все сообщения         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Предоставление пользователям разрешения на редактирование собственных сообщений         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Разрешение пользователям удалять собственные сообщения         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Позволяет пользователям в закрытом чате         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |

<sup>1</sup> устарело для гостя. Теперь можно управлять включением и отключением гостя в центре администрирования Microsoft Teams. В ближайшее время вы не сможете включать и отключать группы для бизнеса Enterprise, edu Student и edu. Для этого необходимо назначить лицензии в центре администрирования Microsoft 365. Ознакомьтесь со сведениями о том [, как управлять доступом пользователей к Microsoft Teams](user-access.md).
<br><br>
<sup>2</sup> для корпоративных пользователей делятся следующим образом:

- Разрешите пользователям неопубликованного приложения, которыми можно управлять на уровне пользователей в [TeamsAppSetupPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps).
- Разрешить пользователям в клиенте взаимодействовать с пользовательскими приложениями, которыми можно управлять на уровне клиента в параметрах приложения в масштабах Организации.

<sup>3</sup> приложения по умолчанию и внешние приложения можно включить и отключить на уровне пользователя в TeamsAppPermissionPolicy. Кроме того, приложения могут быть заблокированы на уровне клиента в параметрах приложения в масштабе организации, которые переопределяют параметры любого пользователя и на уровне клиента.

> [!NOTE]
> Вы продолжаете использовать панель мониторинга "группы" в центре администрирования Microsoft 365 для настройки, связанной с группами и каналами. Параметры приложений будут сохраняться в области Teams в центре администрирования Microsoft 365 и будут перенесены позже.

## <a name="manage-settings-during-the-migration"></a>Управление параметрами во время миграции

Вы можете продолжить изменение параметров в центре администрирования Microsoft 365 и центре администрирования Skype для бизнеса, пока для вашего клиента не будет завершена миграция раздела.

В следующей таблице показано, как управлять функциями во время миграции.

|Компонент  |Центр администрирования Microsoft Teams                      |Центр администрирования Skype для бизнеса (устаревший)  |Центр администрирования Microsoft 365  |
|---------|:---------:|:---------:|:---------:|
|Политики для обмена сообщениями, собраний и динамических событий в Teams     |     X    |         |         |
|Политика обновления Teams     |    X     |         |         |
|Параметры гостя для обмена сообщениями, собраний и голосовой связи     |   X      |         |         |
|Управление жизненным циклом Teams   |    X    |      |       |
|Параметры Teams   |    X    |      |       |
|Параметры внешнего доступа     |    X    |      |       |
|Управление пользователями    |         |         |    X     |
|Аудиоконференции     |    X     |    X     |         |
|Планы звонков     |    X    |    X     |         |
|Телефонная система    |    X    |     X    |         |
|Управление телефонными номерами     |    X    |   X      |         |
|Лицензирование функций голосовой связи в облаке     |         |         |    X     |
|Автосекретари     |    X    |          |         |
|Очередь звонков     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>Управление параметрами после миграции

Когда миграция этих параметров завершится, они будут отключены в центре администрирования Microsoft 365 и центре администрирования Skype для бизнеса, и затем их можно будет управлять в новом центре администрирования Microsoft Teams.
