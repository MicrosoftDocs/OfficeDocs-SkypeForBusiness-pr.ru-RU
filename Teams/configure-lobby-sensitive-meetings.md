---
title: Настройка лобби собраний Microsoft Teams для конфиденциальных собраний
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: Узнайте, как настроить лобби собраний Teams для повышения безопасности конфиденциальных собраний с помощью политик администрирования, меток конфиденциальности и шаблонов собраний.
ms.openlocfilehash: 1905bc337f0260e86b2351da5015b8e1ba641bf4
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800153"
---
# <a name="configure-the-microsoft-teams-meeting-lobby-for-sensitive-meetings"></a>Настройка лобби собраний Microsoft Teams для конфиденциальных собраний

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Лобби собраний — это инструмент, который можно использовать для обеспечения того, чтобы недопустимые люди не допускались на собрания. Проводя различные типы участников в зале ожидания, организаторы собрания могут проверить их и убедиться, что они подходят для участия в собрании.

По умолчанию пользователи в [вашей](guest-access.md) организации и гости допускаются на собрания напрямую, а участники из доверенных доменов и анонимные участники должны ждать в зале ожидания, чтобы их допустил организатор собрания. Организаторы собраний могут изменить этот параметр по умолчанию для каждого создаваемого собрания.

Администратор Teams может управлять лобби и другими связанными параметрами с помощью политик собраний, шаблонов собраний и меток конфиденциальности для настройки взаимодействия с различными пользователями и различными типами собраний.

В следующей таблице перечислены функции, которые можно использовать для управления лоббистской поддержкой вашей организации, и где их можно настроить.

|Параметр|политика Администратор|Метка конфиденциальности|Шаблон|Организатор собрания|
|:------|:----------:|:---------------:|:------:|:---------------:|
|Объявление о присоединении абонентов или выходе из нее|Нет|Нет|Да|Да|
|Анонимные пользователи и абоненты могут начать собрание|Да|Нет|Нет|Нет|
|Анонимные пользователи могут присоединиться к собранию|Да|Нет|Нет|Нет|
|Люди при звонке в можно обойти лобби|Да|Да|Да|Да|
|Кто может обойти лобби|Да|Да|Да|Да|

Сведения об использовании шаблонов и меток конфиденциальности для настройки параметров собрания см. [в разделах Обзор пользовательских шаблонов собраний в Microsoft Teams](custom-meeting-templates-overview.md) и [Использование меток конфиденциальности для защиты элементов календаря, собраний Teams и чата](/microsoft-365/compliance/sensitivity-labels-meetings).

> [!Note]
> Для параметров собрания в метках конфиденциальности и пользовательских шаблонах собраний требуется Teams премиум.

## <a name="lobby-settings-for-different-types-of-meetings"></a>Параметры лобби для различных типов собраний

Для тех, кто может обойти лобби, доступны следующие параметры:

- Все
- Люди в моей организации, доверенные организации и гости
- Люди в моей организации и гости
- Люди в моей организации
- Люди, которые были приглашены
- Организаторы и соорганизаторы

Хотя организатор собрания обычно выбирает, какой параметр будет использоваться для каждого собрания, можно применить определенный параметр с помощью шаблона собрания или метки конфиденциальности.

Если ваша организация требует, чтобы в определенных типах собраний не присутствовали люди за пределами организации, рассмотрите шаблон собрания, который позволяет только сотрудникам вашей организации обходить лобби. Это гарантирует, что пользователи за пределами организации, которые были случайно приглашены или отправлены по ссылке на собрание, не смогут присоединиться к собранию напрямую.

Если в вашей организации есть собрания, на которых предоставляется общий доступ к конфиденциальным сведениям, и вам нужно убедиться, что в нем участвуют только определенные люди, рекомендуется использовать шаблон собрания или метку конфиденциальности, которая позволяет только организаторам собраний обходить лобби. Это гарантирует, что организаторы могут проверить каждого входящего участника, чтобы убедиться, что они должны присутствовать на собрании. Это также предотвращает начало собрания до присоединения организатора.

Для конфиденциальных собраний в целом рекомендуется использовать **параметр Люди, которые были приглашены**. Это гарантирует, что люди, у которых нет приглашения на собрание (включая перенаправленные приглашения), проходят через зал ожидания. (Организатор собрания также может запретить переадресацию при создании собрания.)

Сведения об совместном использовании шаблонов собраний и меток конфиденциальности см. в статье [Совместное использование шаблонов собраний Teams, меток конфиденциальности и политик администрирования для конфиденциальных собраний](meeting-templates-sensitivity-labels-policies.md).

### <a name="attendees-calling-in-by-phone"></a>Участники звонят по телефону

По умолчанию участники, которые звонят по телефону, проходят через зал ожидания. Администраторы могут изменить это значение по умолчанию, так как **пользователи с телефонным подключением могут обходить политику собраний администратора лобби** . Если вы хотите включить или отключить этот параметр, необходимо использовать шаблон собрания или метку конфиденциальности.

Если существуют обстоятельства, в которых вы хотите разрешить абонентам обходить зал ожидания, организаторы собрания могут управлять этим параметром или применять его с помощью шаблона собрания или метки конфиденциальности.

#### <a name="join-and-leave-notifications"></a>Уведомления о присоединении и выходе из нее

Организаторы собрания могут звонить участникам по телефону, когда они присоединяются к собранию или покидают его. Если вы хотите убедиться, что участники по телефону объявляются для определенных типов собраний, можно применить этот параметр с помощью шаблона собрания.

## <a name="meeting-with-anonymous-participants"></a>Собрание с анонимными участниками

Если вы не разрешаете всем обходить зал ожидания, анонимные участники должны пройти через зал ожидания для участия в собрании. Затем организаторы собраний могут решить, следует ли принимать этих участников.

Если ваша организация вообще не разрешает анонимным участникам присоединяться к собраниям, вы можете отключить параметр **Анонимные пользователи могут присоединяться к собранию** в Центре администрирования Teams. Дополнительные сведения см. [в статье Управление параметрами собраний в Microsoft Teams](/microsoftteams/meeting-settings-in-teams).

Если в вашей организации есть определенные группы, например маркетинговые, которым необходимо организовать собрания с анонимными участниками, а другие, например исследования, которые не должны, можно использовать политики собраний Teams для настройки анонимного присоединения к собранию для разных групп. (Чтобы это работало, необходимо включить параметр **Анонимные пользователи могут присоединиться к собранию** , упомянутому выше.) Дополнительные сведения см. в разделе [Параметры политики собрания— участники & гостей](/microsoftteams/meeting-policies-participants-and-guests).

## <a name="related-topics"></a>См. также

[Настройка собраний Teams с тремя уровнями защиты](configure-meetings-three-tiers-protection.md)

[Управление внешними собраниями и чатом в Microsoft Teams](/microsoftteams/manage-external-access)