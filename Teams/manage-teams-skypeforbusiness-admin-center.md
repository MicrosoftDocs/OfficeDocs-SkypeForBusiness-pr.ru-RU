---
title: Управление Teams при переходе на новую версию Центра администрирования Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Узнайте, как управлять параметрами на уровне клиента и пользователями для Teams во время перехода из центра администрирования Microsoft 365 в новый центр администрирования Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.dashboard.helparticle.manageteamsnewadmincenter
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: 0d473ffa67b21c4ec3a160a8687a1688ea1d1cf5
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "37564787"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Управление Teams при переходе на новую версию Центра администрирования Microsoft Teams
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>Что нового в центре администрирования Microsoft Teams?  

Новые возможности центра администрирования предоставляют единый интерфейс для управления группами и Skype для бизнеса. Мы предлагаем дополнительные функции, сквозное представление и возможность управлять параметрами групп на уровне пользователя.

![Снимок экрана: центр администрирования Microsoft Teams.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Параметры, перенесенные в новый центр администрирования Microsoft Teams

В приведенной ниже таблице указаны разделы, которые были перенесены, и показана связь между текущими параметрами и политиками на новом портале администрирования.

|Раздел "Teams" в центре администрирования Microsoft 365  |Имя параметра (уровень клиента)  |Политика центра администрирования Microsoft Teams   |Level (уровень): клиент или пользователь   |
|---------|---------|---------|---------|
|Общий     |Показать организационную диаграмму в личном профиле        |  [теамсклиентконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  Клиента       |
|Общий     |Использование Skype для бизнеса для получателей, не имеющих групп         |[теамсклиентконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиента         |
|Интеграция электронной почты     |Разрешение пользователям отправлять сообщения электронной почты по каналам         |[теамсклиентконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиента         |
|Интеграция электронной почты     |Список разрешенных отправителей         |[теамсклиентконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |Клиента         |
|Настраиваемое облачное хранилище     |Полем         |[теамсклиентконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиента         |
|Настраиваемое облачное хранилище     |Данных        |[теамсклиентконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиента         |
|Настраиваемое облачное хранилище     |Google диск        |[теамсклиентконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиента         |
|Настраиваемое облачное хранилище     |шарефиле        |[теамсклиентконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиента         |
|Параметры по типу пользователя и лицензии     |Включение и отключение Microsoft Teams для всех пользователей          |Устаревший<sup>1</sup>        |         |
|Группы и каналы     |         |Перенаправляет Управление группами Azure Active Directory (то же, что и текущий интерфейс).              |Пользователь         |
|Группы и каналы     |         |Перенаправление на управление группами AAD (то же, что и текущий интерфейс).             |Пользователь          |
|Приложения|Включение новых внешних приложений по умолчанию|Параметры приложения в масштабе Организации|Клиента|
|Приложения|Разрешить внешние приложения|Параметры приложения в масштабе Организации|Клиента|
|Приложения|Разрешение неопубликованных приложений для внешних приложений<sup>2</sup>|[теамсаппсетупполици](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|Пользователь|
|Приложения|Приложения по умолчанию<sup>3</sup>|теамсапппермиссионполици|Пользователь|
|Приложения|Внешние приложения<sup>3</sup>|теамсапппермиссионполици|Пользователь|
|Звонки и собрания     |Разрешить планирование для частных собраний         |[теамсмитингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Пользователь          |
|Звонки и собрания     |Разрешить рекламный канал обсудим         |[теамсмитингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Пользователь          |
|Звонки и собрания     |Разрешить планирование для собраний канала         |[теамсмитингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Пользователь          |
|Звонки и собрания     |Разрешение видеороликов в собраниях         |[теамсмитингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Пользователь          |
|Звонки и собрания     |Разрешение демонстрации экрана в собраниях         |[теамсмитингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Пользователь          |
|Звонки и собрания     |Разрешить частный Звонок         |[TeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |Пользователь          |
|Обмен сообщениями     |Включение GIF, чтобы пользователи могли добавлять в беседы GIF-файлы         |[теамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Рейтинг контента         |[теамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Включение мемов, которые пользователи могут редактировать и добавлять в беседы         |[теамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Включение поддержки наклеек, которые пользователи могут редактировать и добавлять в беседы         |[теамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Разрешить владельцам удалять все сообщения         |[теамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Предоставление пользователям разрешения на редактирование собственных сообщений         |[теамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Разрешение пользователям удалять собственные сообщения         |[теамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Позволяет пользователям в закрытом чате         |[теамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |

<sup>1</sup> устарело для гостя. Теперь можно управлять включением и отключением гостя в центре администрирования Microsoft Teams. В ближайшее время вы не сможете включать и отключать группы для бизнеса Enterprise, edu Student и edu. Для этого необходимо назначить лицензии в центре администрирования Microsoft 365. Ознакомьтесь со сведениями о том [, как управлять доступом пользователей к Microsoft Teams](user-access.md).
<br><br>
<sup>2</sup> для корпоративных пользователей делятся следующим образом:

- Разрешите пользователям неопубликованного приложения, которыми можно управлять на уровне пользователей в [теамсаппсетупполици](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps).
- Разрешить пользователям в клиенте взаимодействовать с пользовательскими приложениями, которыми можно управлять на уровне клиента в параметрах приложения в масштабах Организации.
 
<sup>3</sup> приложения по умолчанию и внешние приложения можно включить и отключить на уровне пользователя в теамсапппермиссионполици. Кроме того, приложения могут быть заблокированы на уровне клиента в параметрах приложения в масштабе организации, которые переопределяют параметры любого пользователя и на уровне клиента. 

> [!NOTE]
> Вы продолжаете использовать панель мониторинга "группы" в центре администрирования Microsoft 365 для настройки, связанной с группами и каналами. Параметры приложений будут сохраняться в области Teams в центре администрирования Microsoft 365 и будут перенесены позже. 

## <a name="manage-settings-during-the-migration"></a>Управление параметрами во время миграции

Вы можете продолжить изменение параметров в центре администрирования Microsoft 365 и центре администрирования Skype для бизнеса, пока для вашего клиента не будет завершена миграция раздела. 

В следующей таблице показано, как управлять функциями во время миграции.

|Функция  |Центр администрирования Microsoft Teams                      |Центр администрирования Skype для бизнеса (устаревший)  |Центр администрирования Microsoft 365  |
|---------|:---------:|:---------:|:---------:|
|Политики для обмена сообщениями, собраний и динамических событий в Teams     |     X    |         |         |
|Политика обновления Teams     |    X     |         |         |
|Параметры гостя для обмена сообщениями, собраний и голосовой связи     |   X      |         |         |
|Управление жизненным циклом Teams   |    X    |      |       |
|Параметры Teams   |    X    |      |       |
|Параметры внешнего доступа     |    X    |      |       |
|Управление пользователями    |         |         |    X     |    
|Аудиоконференции     |    X     |    X     |         |
|Планы звонков     |         |    X     |         |
|Телефонная система    |         |     X    |         |
|Управление телефонными номерами     |         |   X      |         |
|Лицензирование функций голосовой связи в облаке     |         |         |    X     |
|Автосекретари     |         |    X     |         |
|Очередь звонков     |         |    X     |         |

## <a name="manage-settings-after-the-migration"></a>Управление параметрами после миграции

Когда миграция этих параметров будет завершена, они будут отключены в центре администрирования Office 365 и центре администрирования Skype для бизнеса, и они смогут управляться в новом центре администрирования Microsoft Teams.


## <a name="edu-migration-june-july-2019"></a>Миграция EDU за июнь 2019

В течение июня и июль 2019 оставшиеся клиенты EDU будут перенесены из старого интерфейса администратора (в центре администрирования Microsoft 365) в центр администрирования Teams. Просмотрите центр сообщений (в центре администрирования Microsoft 365), чтобы узнать, когда вы будете перенесены. Ниже приведены сведения, которые вы увидите после миграции.

|Раздел "Teams" в центре администрирования Microsoft 365  |Имя параметра (уровень клиента)  |Политика центра администрирования Microsoft Teams   |Level (уровень): клиент или пользователь   |
|---------|---------|---------|---------|  
| Обмен сообщениями  |Владельцы могут удалять отправленные сообщения |[теамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Пользователь |
| Обмен сообщениями | Пользователи могут удалять отправленные сообщения |[теамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Пользователь |
| Обмен сообщениями  | Пользователи могут редактировать отправленные сообщения |[теамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)  |Пользователь|
| Обмен сообщениями | Разрешить пользователям общаться |[теамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Пользователь |
| Обмен сообщениями | Использование Giphy в беседах | [теамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Пользователь |
| Обмен сообщениями | Оценка содержимого GIF | [теамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Пользователь |
| Обмен сообщениями | Использование мемов в беседах  |[теамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Пользователь |
| Обмен сообщениями | Использование наклеек в беседах |[теамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Пользователь |

Кроме того, ниже указаны параметры, доступные только в центре администрирования Microsoft Teams.

|Имя параметра | Политика центра администрирования Microsoft Teams | Level (уровень): клиент или пользователь
|-------------|-------------------------------------|---------|
|Разрешить предварительный просмотр URL-адресов | [теамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Пользователь |
|Разрешение пользователям удалять пользователей из группового чата |[теамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Пользователь |
|Разрешить иммерсивное средство чтения для просмотра сообщений |[теамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)| Пользователь |
|Разрешить пользователям переводить сообщения |[теамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)| Пользователь |
|Уведомления о прочтении | [теамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Пользователь |
|Пользователи могут отправлять уведомления о приоритетах | [теамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Пользователь |
|Создание голосовых сообщений |[теамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/new-csteamsmessagingpolicy?view=skype-ps)| Пользователь |
|На мобильных устройствах отображение избранных каналов над последними чатами |[теамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/new-csteamsmessagingpolicy?view=skype-ps)| Пользователь |
