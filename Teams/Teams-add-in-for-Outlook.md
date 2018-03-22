---
title: Использование надстройки "Собрание Microsoft Teams" в Outlook
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: Microsoft Teams устанавливает в Outlook надстройку, которая позволяет пользователям планировать собрания Microsoft Teams из Outlook.
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 811c27a48a0e9bbccfbea7ac12e54ef0697b3f2b
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Использование надстройки "Собрание Teams" в Outlook
=======================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Надстройка "Собрание Teams" автоматически устанавливается для пользователей Windows, на компьютерах которых есть Microsoft Teams и Office 2013 либо Office 2016. Надстройка "Собрание Teams" отображается в ленте "Календарь Outlook". 

![Снимок экрана с надстройкой Microsoft Teams в ленте Outlook.](media/Teams-add-in-for-Outlook.png)

Если надстройка "Собрание Teams" не отображается, попросите пользователей закрыть Outlook и Microsoft Teams, затем перезапустить клиент Microsoft Teams, войти в него и перезапустить клиент Outlook (именно в таком порядке).

> [!NOTE]
> Надстройка "Собрание Teams" для Outlook в настоящее время недоступна для пользователей Mac.

## <a name="authentication-requirements"></a>Требования к проверке подлинности

Чтобы использовать надстройку "Собрание Teams", пользователи должны войти в Microsoft Teams с помощью современной проверки подлинности. Если не использовать этот метод проверки подлинности для входа, работа с клиентом Microsoft Teams будет возможна, но нельзя будет планировать собрания Microsoft Teams по сети с помощью настройки Outlook. Решить эту проблему можно одним из следующих способов:

- Если для вашей организации не настроена современная проверка подлинности, настройте ее.
- Если современная проверка подлинности настроена, но отключена в диалоговом окне, попросите пользователей повторить вход с помощью многофакторной проверки подлинности.

Дополнительные сведения о настройке проверки подлинности: [Модели удостоверений и проверка подлинности в Microsoft Teams](identify-models-authentication.md).

## <a name="enable-private-meetings"></a>Активация частных собраний

Для развертывания подключаемого модуля нужно разрешить планирование частных собраний в [Центре администрирования Office 365](https://portal.office.com/adminportal/home).

![Снимок экрана с параметрами раздела "Звонки и собрания" в Центре администрирования Office 365.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

Клиент Microsoft Teams устанавливает нужную надстройку, определяя, требуется ли пользователям 32- или 64-разрядная версия.

> [!NOTE]
> Для получения новейшей версии надстройки пользователям может потребоваться перезапустить Outlook после установки или обновления Microsoft Teams.

## <a name="other-considerations"></a>Другие особенности

Разработка функционала надстройки "Собрание Teams" продолжается, так что помните о следующем:
- Некоторые функции собраний по сети, такие как запись, опрос и доска, пока недоступны.
- Параметры собрания сейчас недоступны.
- Сейчас вы можете приглашать в собрания только участников из своей компании, но не внешних пользователей.
- Надстройка предназначена для запланированных собраний с конкретными участниками, а не для собраний в канале. Собрания в канале нужно планировать в Microsoft Teams. Надстройка "Собрание Teams" в Outlook сейчас доступна только пользователям Windows, но в ближайшее время будет реализована поддержка Mac.
- Надстройка не будет работать, если прокси-сервер проверки подлинности находится по сетевому пути пользовательского ПК и служб Microsoft Teams.

Общие указания по отключению надстроек: [Просмотр и установка надстроек, а также управление ими в приложениях Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).

Получите дополнительные сведения о [собраниях и звонках в Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).

