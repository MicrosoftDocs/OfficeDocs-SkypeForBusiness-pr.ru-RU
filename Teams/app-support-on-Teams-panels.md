---
title: Microsoft Teams приложений и бизнес-приложений на Teams панели
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 8/5/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: В этой статье описана поддержка Teams и LOB-приложений.
ms.collection:
- M365-voice
- M365-collaboration
- skype-for-business-itpro
- skype-for-business-online
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb6950bbb78bf04b01194bbab5ec6d9030a53137
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235744"
---
# <a name="microsoft-teams-appsline-of-business-lob-app-support-on-teams-panels"></a>Microsoft Teams приложений и бизнес-приложений на Teams панели

Teams панели добавляют поддержку Teams приложений и бизнес-приложений. Это позволит предприятиям добавлять дополнительные возможности на панелях в зависимости от потребностей организации. Этот выпуск поддерживает статический веб-контент.

> [!IMPORTANT]
> Эта функция доступна только после обновления панелей Teams устройств. Для поддержки приложений на панелях Teams требуется версия Teams 1449/1.0.97.202107060 Teams 1 или более новая.

## <a name="set-up-and-manage-teams-panels-apps-in-teams-admin-center"></a>Настройка приложений панели Teams панели Teams центре администрирования 

Microsoft Teams приложения используют основные сведения, общие инструменты и надежные процессы в месте сбора, обучения и работы. Teams работают [интегрированные возможности.](/platform/concepts/capabilities-overview) Теперь У ИТ-администратора есть возможность выбрать приложения, которые нужно включить в устройство Teams панели Teams и настроить разрешения через Teams администрирования.

Теперь вы можете использовать приложения Teams на Teams панели и настроить пользовательский интерфейс в зависимости от потребностей организации. Вы можете решить, какое веб-приложение смогут получать доступ к представлениям и использовать их, а также определить их приоритет. В настоящее время некоторые возможности, такие как бот и возможности обмена сообщениями, не поддерживаются. Узнайте больше о Teams приложениях и управлении устройствами в Microsoft Teams.

## <a name="manage-apps-on-teams-panels-in-teams-admin-center"></a>Управление приложениями на Teams панели Teams центре администрирования

**Примечание.** Для доступа к Центру администрирования Teams администратором службы или администратором Teams службы.

Конечные пользователи могут просматривать приложения на панели Teams, но не устанавливать их. Как администратор вы можете просматривать и управлять всеми приложениями Teams для своей организации с помощью Teams администрирования. Узнайте больше о том, как управлять приложениями в центре администрирования Microsoft Teams на странице **Управление приложениями.** На **странице Управление приложениями** в Центре администрирования Teams также можно добавить [пользовательские приложения.](/manage-apps#publish-a-custom-app-to-your-organizations-app-store)

После настройки приложений вы [](/teams-app-permission-policies) можете использовать политики [](/teams-app-setup-policies) разрешений приложений и политики настройки приложений для настройки работы с приложениями для определенных учетных записей комнат в организации.

## <a name="pin-apps-on-teams-panels-with-app-setup-policies"></a>Закрепление приложений на Teams с помощью политик настройки приложений

Поскольку Teams предлагает возможность отображения широкого диапазона приложений, администраторы могут решить, какие приложения наиболее важны для организации, и закрепить только эти приложения на домашнем экране Teams панели для быстрого доступа.  Если есть более пяти закрепленных приложений или всех незакрепированных приложений, они будут отображаться под **экраном "Еще".** Корпорация Майкрософт рекомендует создать настраиваемую политику настройки приложений специально для Teams панелей.

![Снимок экрана: страница политик настройки приложений в пользовательском интерфейсе.](media/appsetup1.png) 

Чтобы управлять закрепленными приложениями, которые отображаются на панелях Teams, войдите в Центр  администрирования Teams для своей организации и перейдите в Teams политики установки приложений Выберите или Создайте новые приложения с закрепленными \>  \>  \> **политиками**.

![Снимок экрана: раздел закрепленных приложений в пользовательском интерфейсе.](media/appsetup2.png) 

Корпорация Майкрософт рекомендует  отключить Upload настраиваемые  приложения и разрешить закрепление пользователей для Teams приложения на Teams панелях.

Дополнительные информацию о закреплении приложений см. в [управлении политиками настройки приложений.](/teams-app-setup-policies)

## <a name="manage-apps-display-order-in-teams-panels"></a>Управление порядком отображения приложений на Teams панели 

![Снимок экрана: раздел приложений в пользовательском интерфейсе.](media/appsetup3.png) 

Чтобы настроить порядок отображения приложений на панелях Teams, войдите в Центр администрирования Teams для своей  организации и перейдите в Teams политики установки приложений Выберите закрепленные приложения \>  \>  \> **политики:** **Вверх/вниз**.

## <a name="assigning-setup-policies-to-a-room-resource-account"></a>Назначение политик настройки учетной записи ресурса комнаты

После создания политики настройки администратор должен назначить эту политику учетной записи ресурса комнаты, которая будет вписна в Teams панели. Дополнительные сведения: [Назначение политик пользователям и группам.](/assign-policies-users-and-groups)

## <a name="faq"></a>Вопросы и ответы

### <a name="how-long-does-it-take-for-teams-panels-to-get-the-new-or-updated-app-setup-policies"></a>Сколько времени займет Teams панели для получения новых или обновленных политик настройки приложений?

После изменения или назначения новых политик в Центре Teams администрирования может занять до 24 часов, чтобы изменения вступили в силу. Администраторы могут попытаться выйти или войти из панели, нажать значок Параметры и  вернуться на домашний экран, чтобы попытаться обновить политики. 

### <a name="what-is-the-ordering-of-the-apps-on-the-more-screen"></a>Порядок приложений на экране "Еще"

На странице **Дополнительные** приложения сначала появятся закрепленные приложения. После этого все остальные установленные приложения будут отображаться в алфавитном порядке.

### <a name="why-are-bot-apps-not-showing-up-on-teams-panels"></a>Почему приложения-боты не отображаются на Teams панели?

В настоящее время поддерживается только статическое содержимое веб-вкладок.

### <a name="why-are-native-teams-apps-such-as-calendar-and-tasks-not-appearing-on-teams-panels"></a>Почему на панели Teams не отображаются приложения Teams Teams, такие как календарь и задачи?

Приложения Teams, такие как "Календарь" и "Задачи", не Teams панели.

### <a name="in-the-teams-admin-center-under-the-setup-policies-section-what-is-the-difference-between-installed-apps-and-pinned-apps"></a>В Teams в разделе политики настройки в чем разница между установленными и закрепленными приложениями?

Для Teams панелей Майкрософт рекомендует использовать закрепленные приложения, чтобы администратор мог выбрать нужное приложение и изменить его порядок.

**Примечание.** Некоторые приложения не поддерживают закрепление приложений. Обратитесь к разработчику приложения, чтобы включить закрепление приложений.

### <a name="why-are-other-apps-appearing-in-the-more-screen-even-though-they-are-not-part-of-the-installed-or-pinned-apps-in-the-teams-app-setup-policy-section"></a>Почему другие приложения отображаются на экране "Еще", хотя они не являются частью установленных или закрепленных приложений в разделе политики настройки Teams приложений?

Если приложения были ранее установлены с помощью других политик приложений или вручную в классических или веб-клиентах Teams для учетной записи ресурса комнаты, используемой на панелях Teams, администратору может потребоваться войти в учетную запись ресурса комнаты в Teams и вручную удалить приложения, щелкнув приложение правой кнопкой мыши и выбрав удалить **.**

### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Почему я не могу найти приложение в области "Добавление закрепленных приложений"?

Не все приложения можно закрепить на Teams с помощью политики настройки приложений. Некоторые приложения могут не поддерживать эту функцию. Чтобы найти приложения, которые можно закрепить, найдите их в области Добавление **закрепленных** приложений. Дополнительные сведения можно найти в часто задаваемом [вопросе в области Работа с](/teams-app-setup-policies#why-cant-i-find-an-app-in-the-add-pinned-apps-pane)политиками настройки приложений.

### <a name="why-am-i-seeing-an-allow-user-pinning-pop-up-in-the-setup-policies-panel-after-i-turn-off-allow-user-pinning"></a>Почему после отключения "Разрешить закрепление пользователей" в панели "Политики настройки" я вижу всплывающее "Разрешить закрепление пользователей?".

![Снимок экрана: раздел политики настройки в пользовательском интерфейсе с всплывающим подтверждением того, что активна закрепление пользователя.](media/appsetup4.png) 

Такое поведение является ожидаемым для устройства в общем пространстве и помогает предотвратить непреднамеренное закрепление приложения.