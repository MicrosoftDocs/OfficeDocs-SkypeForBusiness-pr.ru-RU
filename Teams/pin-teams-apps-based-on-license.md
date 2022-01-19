---
title: Подгоняйте Teams приложений на основе лицензии
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Узнайте, как закрепить Teams приложения для пользователей в организации на основе лицензии.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: a82dbf888fcd6fd0b05816e3edb390b79c9a9e3f
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055319"
---
# <a name="tailor-your-teams-apps-based-on-license"></a>Подгоняйте Teams приложений на основе лицензии

> [!NOTE]
> [!INCLUDE [new-feature-coming-soon-section](includes/new-feature-coming-soon-section.md)]

> [!NOTE]
> В настоящее время эта функция применяется к F-лицензиям. Поэтому в этой статье основное внимание уделяется работе сотрудников с передней линией. В будущем будут поддерживаться и другие типы лицензий.

## <a name="overview"></a>Обзор

Teams позволяет закрепить приложения на основе лицензии. Когда пользователь вошел в Teams с включенным индивидуальным интерфейсом приложения, он получает интерфейс приложения, разработанный с учетом его лицензии.

Эта функция предоставляет пользователям наиболее подходящие приложения Teams без каких-либо действий со стороны администратора.

## <a name="tailored-app-experience"></a>Индивидуальный опыт работы с приложениями

Приложения закреплены на панели приложений, которая находится в Teams и в нижней части мобильных клиентов Teams (iOS и Android).

Приложения, закрепленные для пользователей с F-лицензией:

- Действие
- Чат
- Teams
- Смены
- Задачи
- Рация

## <a name="admin-controls"></a>Элементы управления администратором

> [!NOTE]
> Чтобы эта функция вступила в силу, в глобальной политике настройки приложений (по умолчанию [в](teams-app-setup-policies.md) организации) должно быть включено закрепление пользователей.

Настраиваемая функция интерфейса приложения  управляется параметром Показывать специализированные приложения на [](manage-apps.md#manage-org-wide-app-settings) основе лицензий в масштабе организации на странице Управление приложениями в Центре администрирования Teams приложений. Если эта функция есть, все пользователи в организации, у которых есть F-лицензия, получат индивидуальный опыт работы с приложением.

Помните, что приоритет имеют любые настраиваемые политики настройки приложений, которые назначены пользователям. Это означает, что если пользователю уже назначена настраиваемая политика настройки приложений, он получает конфигурацию, заданной в настраиваемой политике настройки приложения. Дополнительные информацию о том, как эта функция работает с существующими политиками настройки приложений, которые вы применили в организации, см. в разделе [Сценарии](#scenarios) этой статьи.

По умолчанию эта функция включена. Однако если вы не хотите использовать специализированные приложения, предоставляемые корпорацией Майкрософт, вы можете отключить эту функцию. Чтобы отключить или включить эту функцию:

1. В левой области навигации Центра администрирования Microsoft Teams перейдите в Teams **приложения Управление** приложениями , а затем выберите Параметры приложений для  >  всей **организации.**
2. В **области Индивидуальные**  приложения переключите переключатель Показывать специализированные приложения на основе лицензий в переключатель **Выкл.** или **Вкл.**.

    :::image type="content" source="media/pin-teams-apps-based-on-license.png" alt-text="Снимок экрана: страница "Управление приложениями" с параметром "Показывать специализированные приложения на основе лицензии для всей организации"" lightbox="media/pin-teams-apps-based-on-license.png":::

## <a name="scenarios"></a>Scenarios

Из этой таблицы вы узнаете, как работает специализированная функция работы с приложениями в различных сценариях, в том числе при применении существующих политик настройки приложений.

|Если...  |Затем... |
|---------|---------|
|У пользователя есть глобальная политика настройки приложений, и эта функция уже установлена.     | Пользователь получает индивидуальный интерфейс приложения.        |
|У пользователя есть настраиваемая политика настройки приложения, и эта функция уже установлена.    |Пользователь получает конфигурацию, заданная в настраиваемой политике настройки приложения.          |
|Эта функция будет в сети, и вы обновили глобальную политику настройки приложений.     |Пользователь получает индивидуальный интерфейс приложения на основе своей лицензии. Приложения, определенные в политике настройки глобального приложения, по-прежнему закреплены и отображаются в списке закрепленных приложений.          |
|Эта функция отключена.   | Пользователь получает интерфейс, определенный в назначенной ему политике настройки глобального приложения или настраиваемой политике настройки приложений.          |
|У пользователя есть лицензия на E, A или G, и эта функция уже в сети.   | Пользователь не получает специального интерфейса приложения. В настоящее время индивидуальный доступ к приложению применяется только к пользователям с F-лицензией.        |
|Приложение в пользовательском интерфейсе блокируется для пользователя или для вашей организации.      |Индивидуальный опыт работы приложения с учетом политики разрешений приложений. Если приложение заблокировано, пользователи не увидят его.           |
|Приложение в специальной конфигурации уже определено в политике настройки приложения, и эта функция уже установлена. |Приложение закреплено в порядке, определенном в специальном приложении.        |

> [!NOTE]
> Вы не можете изменить приложения или их порядок в специальном приложении. В настоящее время, если вы хотите внести изменения, вы можете настроить собственный пользовательский опыт. Для этого сначала отключите эту функцию. Затем [создайте настраиваемую политику настройки](teams-app-setup-policies.md)приложения и [назначьте ее пользователям или группам.](assign-policies-users-and-groups.md)

## <a name="related-articles"></a>Статьи по теме

- [Управление политиками настройки приложений в Teams](teams-app-setup-policies.md)
- [Управление политиками разрешений для приложений в Teams](teams-app-permission-policies.md)