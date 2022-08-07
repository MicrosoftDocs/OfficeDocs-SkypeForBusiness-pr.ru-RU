---
title: Управление Teams с помощью политик
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Изучите политики Teams.
audience: admin
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: acaa1280e00ad2e86a49c2bbd8e7f4464bd0c0e7
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268764"
---
# <a name="manage-teams-with-policies"></a>Управление Teams с помощью политик

Политики являются важной частью управления Teams. Используйте эту статью, чтобы узнать, как использовать политики для преимущества вашей организации.

## <a name="what-you-use-policies-for"></a>Для чего используются политики

Политики используются для выполнения многих задач в организации в различных областях, таких как обмен сообщениями, собрания и приложения. Некоторые из действий, которые можно сделать, включают разрешение пользователям планировать собрания в канале teams, позволяя пользователям изменять отправленные сообщения и управлять возможностью пользователей закреплять приложения на панели приложений Teams.

## <a name="how-to-assign-policies"></a>Назначение политик

Политики можно назначать несколькими способами в зависимости от того, что пытается выполнить ваша организация. Вы можете создавать и просматривать назначения в Центре администрирования Teams.

:::image type="content" source="media/group-policy-assignment.png" alt-text="Снимок экрана: назначение групповой политики Teams." lightbox="media/group-policy-assignment.png":::

Дополнительные сведения о назначении политик см. [здесь](policy-assignment-overview.md).

> [!NOTE]
> Чтобы отменить назначение политик, можно массово удалить назначения для всех пользователей, непосредственно назначенных политике. Дополнительные сведения см. в разделе "Массовое чтение [политик отмены назначения"](assign-policies-users-and-groups.md#unassign-policies-in-bulk).

## <a name="how-to-manage-policies"></a>Управление политиками

Управление политиками можно с помощью Центра администрирования Microsoft Teams или [PowerShell](./teams-powershell-managing-teams.md#manage-policies-via-powershell).

Например, политика установки приложения позволяет разрешить пользователям отправлять пользовательские приложения, устанавливать приложения от имени пользователей и закреплять приложения на панели приложений Teams. Эти политики настраиваются в Центре администрирования Teams.

:::image type="content" source="media/app-setup-policy.png" alt-text="Снимок экрана: политика установки приложения." lightbox="media/app-setup-policy.png":::

Кроме того, политику собраний можно использовать для управления параметрами звука и видео в собраниях Teams, такими как транскрибирование, облачные записи и АУДИО-аудио-видео.

:::image type="content" source="media/engineering-meeting-policy.png" alt-text="Снимок экрана: политика собрания." lightbox="media/engineering-meeting-policy.png":::

### <a name="teams-for-education"></a>Teams для образовательных учреждений

Вы также можете использовать мастер [политики Teams для образования](easy-policy-setup-edu.md), чтобы легко настраивать политики для среды обучения и управлять ими.

:::image type="content" source="media/easy-policy-setup-quick-setup.png" alt-text="Снимок экрана: Teams для образования политики." lightbox="media/easy-policy-setup-quick-setup.png":::

## <a name="types-of-policies"></a>Типы политик

С помощью Microsoft Teams можно управлять следующими политиками.

Тип политики | Описание
------------|------------
[Пакеты политик](manage-policy-packages.md) | Пакет политики в Microsoft Teams — это набор стандартных политик и параметров, которые можно назначить пользователям с аналогичными ролями в организации.
[Политики собрания](meeting-policies-overview.md) | Политика собраний используется для управления функциями, доступными участникам собрания для собраний, запланированных пользователями в вашей организации. Политики собраний включают следующие разделы.<br> — Политики аудио- и видеосвязи<br> — Политики общего доступа к содержимому и экрану<br> — Участники, гости и политики доступа<br> — Общие политики
[Политики голосовой связи и звонков](voice-and-calling-policies.md)| Политики голосовой связи и звонков управляют этими параметрами с помощью таких команд, как экстренные вызовы, маршрутизация звонков и идентификатор вызывающего абонента.
[Политики приложений](app-policies.md)| Политики приложений используются для управления приложениями в Microsoft Teams. Администраторы могут разрешить или заблокировать приложения, которые пользователи могут устанавливать, закреплять приложения на панели приложений Teams пользователя и устанавливать приложения от имени пользователей.
[Политики обмена сообщениями](messaging-policies-in-teams.md)| Политики обмена сообщениями могут управлять доступностью функций чата и каналов.

## <a name="related-topics"></a>Статьи по теме

* [Назначение политик в Teams — начало работы](policy-assignment-overview.md)
* [Управление политиками обратной связи в Microsoft Teams](manage-feedback-policies-in-teams.md)
* [Управление политиками teams в Microsoft Teams](teams-policies.md)
* [Подготовка к трансляциям в Microsoft Teams](teams-live-events/set-up-for-teams-live-events.md)
* [Teams для образования политик и пакетов политик](policy-packages-edu.md)