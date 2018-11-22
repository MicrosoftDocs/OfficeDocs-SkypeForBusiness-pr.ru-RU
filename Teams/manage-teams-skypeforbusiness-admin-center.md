---
title: Управление группами во время перехода на новые группами Майкрософт & Скайп по центру администрирования Business
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Понять, как управлять всей клиента и пользовательские параметры для группы во время перехода от групп работы в центре администрирования Office 365 для новых групп Майкрософт & Скайп по центру администрирования бизнес.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: b3305efee9636dfff391fc9a851227cf215b719a
ms.sourcegitcommit: e93b12f5ebaad1140d7df798b5e0647197b9213d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2018
ms.locfileid: "26649535"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams--skype-for-business-admin-center"></a>Управление группами во время перехода на новые группами Майкрософт & Скайп по центру администрирования Business
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams--skype-for-business-admin-center"></a>Что такое новых групп Майкрософт & Скайп по центру администрирования бизнеса?  

Новые возможности Центр администрирования будет предоставлять единое решение для управления группами и Скайп для бизнеса. Мы получили возможность работать дополнительные функциональные возможности, полезные сведения о начала до конца и возможность управлять параметрами группы на уровне пользователя.

![Снимок экрана с группами Майкрософт & Скайп по центру администрирования бизнеса.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams--skype-for-business-admin-center"></a>Параметры перенесены в новых групп Майкрософт & Скайп по центру администрирования бизнеса

В следующей таблице указаны разделы на взаимодействие с группами, которые были перенесены и показана взаимосвязь между текущие параметры и политики в новый портал администрирования.

|Раздел групп в центре администрирования Office 365  |Имя параметра (уровень клиента)  |Группами Майкрософт & Скайп для политики Business центра администрирования   |Уровень: Клиента или пользователя   |
|---------|---------|---------|---------|
|Общие     |Показать организационные чата в личный профиль        |  [TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  Клиент       |
|Общие     |Используйте Скайп для получателей, у которых нет команд для бизнеса         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиент         |
|Интеграция электронной почты     |Разрешить пользователям отправлять сообщения электронной почты с каналами         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиент         |
|Интеграция электронной почты     |Разрешить отправителей списка         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |Клиент         |
|Настраиваемое облачное хранилище     |Поле         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиент         |
|Настраиваемое облачное хранилище     |Общего банка данных        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиент         |
|Настраиваемое облачное хранилище     |Диск Google        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиент         |
|Настраиваемое облачное хранилище     |ShareFile        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Клиент         |
|Введите параметры пользователя и лицензии     |Включить группами Майкрософт включено или отключено для всех пользователей          |Устаревшие<sup>1</sup>        |         |
|Команды и каналы     |         |Перенаправляет Azure Active Directory Управление групповой (то же, что текущий взаимодействия).              |Пользователь         |
|Команды и каналы     |         |Перенаправления на управление группами AAD (то же, что текущий взаимодействия).             |Пользователь          |
|Звонки и собрания     |Разрешить планирование для частных собраний         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Пользователь          |
|Звонки и собрания     |Разрешить meetup Ad-hoc канала         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Пользователь          |
|Звонки и собрания     |Разрешить планирование для собраний канала         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Пользователь          |
|Звонки и собрания     |Разрешить видео в собраниях         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Пользователь          |
|Звонки и собрания     |Разрешение экрана общего доступа в собраниях         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Пользователь          |
|Звонки и собрания     |Разрешить частной телефонной         |[TeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |Пользователь          |
|Обмен сообщениями     |Включение Giphy, поэтому пользователи могут добавлять рисунки в формате GIF беседы         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Оценка содержимого         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Включение memes, который пользователи могут редактировать и добавьте беседы         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Включение наклейки, которые пользователи могут редактировать и добавьте беседы         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Разрешить владельцам для удаления всех сообщений         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Разрешить пользователям изменять собственные сообщения         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Разрешить пользователям удалять собственные сообщения         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |
|Обмен сообщениями     |Позволяет пользователям чата в конфиденциальном режиме         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Пользователь         |

Больше <sup>1</sup> гостем. Включение и отключение гостевой теперь можно управлять группами Майкрософт и Скайп по центру администрирования бизнес. Включение и отключение групп для предприятий, учебы Edu и не факультета Edu ближайшее время. Это должно осуществляться с назначением лицензий в центре администрирования Office 365. [Управление доступом пользователей к группам Microsoft](user-access.md)см.

> [!NOTE]
> Использование панели мониторинга групп в центре администрирования Office 365 для конфигурации, связанные с группами и каналы будет продолжать. Параметры для приложений, будут оставаться в области группы центра администрирования Office 365 и будут перенесены более поздней версии. 

## <a name="manage-settings-during-the-migration"></a>Управление параметрами во время миграции

Можно продолжить изменение параметров в центре администрирования Office 365 и Скайп по центру администрирования Business до завершения для вашего клиента миграции для раздела. 

В следующей таблице показаны которых можно управлять функции во время миграции.

|Функция  |Группами Майкрософт & Скайп по центру администрирования бизнеса                       |Скайп по центру администрирования Business (устаревший)  |Центр администрирования Office 365  |
|---------|:---------:|:---------:|:---------:|
|Команды, системы обмена сообщениями и Live события политики     |     X    |         |         |
|Обновление политики групп     |    X     |         |         |
|Гостевая параметров системы обмена сообщениями, собраний и голосовой связи     |   X      |         |         |
|Управление жизненным циклом групп   |    X    |      |       |
|Параметры команды   |    X    |      |       |
|Параметры внешнего доступа     |    X    |      |       |
|Управление пользователями    |         |         |    X     |    
|Аудиоконференции     |    X     |    X     |         |
|Планы звонков     |         |    X     |         |
|Телефонная система    |         |     X    |         |
|Управление номеров телефонов     |         |   X      |         |
|Лицензирование для облачных функций голосовой связи     |         |         |    X     |
|Автосекретари     |         |    X     |         |
|Очередь звонков     |         |    X     |         |

## <a name="manage-settings-after-the-migration"></a>Управление параметрами после миграции

После завершения миграции эти параметры мы будем отключить в центре администрирования Office 365 и Скайп по центру администрирования бизнес и ими можно управлять нажмите в новых групп Майкрософт & Скайп по центру администрирования бизнеса.


