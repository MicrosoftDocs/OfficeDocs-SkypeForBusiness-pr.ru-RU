---
title: Управление Teams переходом на новый Teams администрирования
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Узнайте, как управлять параметрами клиента и пользователей для Teams во время перехода Teams в Центр администрирования Microsoft 365 к новому Teams центра администрирования.
ms.localizationpriority: medium
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
ms.openlocfilehash: 83b65724099aa46bfe1f1719430e70d8da86ce33
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675091"
---
# <a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Управление Teams при переходе на новую версию Центра администрирования Microsoft Teams

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>Что такое новый Microsoft Teams центра администрирования  

Новый интерфейс Центра администрирования предоставляет единый интерфейс для управления как Teams, так и Skype для бизнеса. Мы предоставляем дополнительные функциональные возможности, сквозную аналитику и возможность управления Teams параметрами на уровне пользователя.

![Снимок экрана: Microsoft Teams центра администрирования.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Параметры в новый центр администрирования Microsoft Teams

В следующей таблице указаны разделы перенесенного Teams и показана связь между текущими параметрами и политиками на новом портале администрирования.

|Раздел Teams в Центр администрирования Microsoft 365  |Имя параметра (уровень клиента)  |Microsoft Teams центра администрирования   |Уровень: клиент или пользователь   |
|---------|---------|---------|---------|
|Общие     |Отображение организационной диаграммы в личном профиле        |  [TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)       |  Арендатор       |
|Общие     |Используйте Skype для бизнеса для получателей, у которых нет Teams         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Арендатор         |
|Интеграция электронной почты     |Разрешить пользователям отправлять сообщения электронной почты в каналы         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Арендатор         |
|Интеграция электронной почты     |Разрешить список отправителей         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)        |Арендатор         |
|Настраиваемое облачное хранилище     |Коробка         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Арендатор         |
|Настраиваемое облачное хранилище     |Dropbox        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Арендатор         |
|Настраиваемое облачное хранилище     |Egnyte        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Арендатор         |
|Настраиваемое облачное хранилище     |Google Диск        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Арендатор         |
|Настраиваемое облачное хранилище     |Sharefile        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Арендатор         |
|Параметры по типу пользователя или лицензии     |Включение Microsoft Teams отключение для всех пользователей          |Не рекомендуется<sup>1</sup>        |         |
|Команды и каналы     |         |Перенаправляет в Azure Active Directory групп (как и в текущем интерфейсе).              |Пользователь         |
|Команды и каналы     |         |Перенаправление на управление группой AAD (то же, что и в текущем интерфейсе).             |Пользователь          |
|Приложения|Включение новых внешних приложений по умолчанию|Параметры приложения для всей организации|Арендатор|
|Приложения|Разрешить внешние приложения|Параметры приложения для всей организации|Арендатор|
|Приложения|Разрешить загрузку неопубликованных внешних приложений<sup>2</sup>|[TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy)|Пользователь|
|Приложения|Приложения по умолчанию<sup>3</sup>|TeamsAppPermissionPolicy|Пользователь|
|Приложения|Внешние приложения<sup>3</sup>|TeamsAppPermissionPolicy|Пользователь|
|Звонки и собрания     |Разрешить планирование для частных собраний         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Пользователь          |
|Звонки и собрания     |Разрешить нерегламентированное собрание каналов         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Пользователь          |
|Звонки и собрания     |Разрешить планирование для собраний канала         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Пользователь          |
|Звонки и собрания     |Разрешение видео на собраниях         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Пользователь          |
|Звонки и собрания     |Разрешить демонстрацию экрана на собраниях         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Пользователь          |
|Звонки и собрания     |Разрешить частные вызовы         |[TeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)        |Пользователь          |
|Обмен сообщениями     |Включите Giphy, чтобы пользователи могли добавлять GIF-файлы в беседы         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Пользователь         |
|Обмен сообщениями     |Оценка содержимого         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Пользователь         |
|Обмен сообщениями     |Включение мемов, которые пользователи могут редактировать и добавлять в беседы         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Пользователь         |
|Обмен сообщениями     |Включение наклеек, которые пользователи могут редактировать и добавлять в беседы         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Пользователь         |
|Обмен сообщениями     |Разрешить владельцам удалять все сообщения         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Пользователь         |
|Обмен сообщениями     |Разрешение пользователям изменять собственные сообщения         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Пользователь         |
|Обмен сообщениями     |Разрешение пользователям удалять собственные сообщения         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Пользователь         |
|Обмен сообщениями     |Позволяет пользователям общаться в частном чате         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Пользователь         |

<sup>1</sup> Не рекомендуется к использованию для гостевой учетной записи. Включением и отключением гостевой службы теперь можно управлять в Microsoft Teams администрирования. Включение и отключение Teams для бизнеса Enterprise, Edu Student и Edu Faculty скоро будет прекращено. Для этого следует назначить лицензии в Центр администрирования Microsoft 365. См[. раздел "Управление доступом пользователей к Microsoft Teams](user-access.md)".
<br><br>
<sup>2 Загрузка</sup> неопубликованных приложений разделяется следующим образом:

- Разрешить пользователю загрузку неопубликованных приложений, которыми можно управлять на уровне пользователя в [TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy).
- Разрешите пользователям в клиенте взаимодействовать с пользовательскими приложениями, которыми можно управлять на уровне клиента в параметрах приложения на уровне организации.

<sup>3</sup> . Приложения по умолчанию и внешние приложения можно включить и отключить на уровне пользователя в TeamsAppPermissionPolicy. Кроме того, приложения могут быть заблокированы на уровне клиента в параметрах приложения на уровне организации, что переопределяет любые параметры на уровне пользователя и клиента.

> [!NOTE]
> Вы продолжите использовать панель мониторинга "Группы" в Центр администрирования Microsoft 365 для настройки, связанной с Teams и каналами. Параметры для приложений останутся в Teams области Центр администрирования Microsoft 365 и будут перенесены позже.

## <a name="manage-settings-during-the-migration"></a>Управление параметрами во время миграции

Вы можете продолжать изменять параметры в Центр администрирования Microsoft 365 и центре администрирования Skype для бизнеса до завершения миграции раздела для вашего клиента.

В следующей таблице показано, где можно управлять функциями во время миграции.

|Функция  |Microsoft Teams центра администрирования                      |Skype для бизнеса центра администрирования (устаревшая версия)  |Центр администрирования Microsoft 365  |
|---------|:---------:|:---------:|:---------:|
|Teams сообщений, собраний и трансляций     |     X    |         |         |
|Teams обновления     |    X     |         |         |
|Параметры гостя для обмена сообщениями, собраний и голосовой связи     |   X      |         |         |
|Teams управления жизненным циклом   |    X    |      |       |
|Teams Параметры   |    X    |      |       |
|Параметры внешнего доступа     |    X    |      |       |
|Управление пользователями    |         |         |    X     |
|Аудиоконференции     |    X     |    X     |         |
|Планы звонков     |    X    |    X     |         |
|Телефонная система    |    X    |     X    |         |
|Телефон управления номерами     |    X    |   X      |         |
|Лицензирование облачных голосовых функций     |         |         |    X     |
|Автосекретари     |    X    |          |         |
|Очередь звонков     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>Управление параметрами после миграции

После переноса этих параметров мы отключим их в Центр администрирования Microsoft 365 и Центре администрирования Skype для бизнеса, а затем их можно будет управлять в новом Microsoft Teams центре администрирования.
