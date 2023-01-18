---
title: Настройка собраний Teams с тремя уровнями защиты
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
- m365solution-overview
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: Узнайте, как настроить собрания Teams для повышения безопасности с помощью трех уровней защиты, чтобы сбалансировать безопасность и упростить совместную работу.
ms.openlocfilehash: 607c4d484df714fd4fba736ffd618aafdbab67d6
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800130"
---
# <a name="configure-teams-meetings-with-three-tiers-of-protection"></a>Настройка собраний Teams с тремя уровнями защиты

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

В статьях этой серии содержатся варианты использования функций соответствия, доступных в Teams и Microsoft 365, для создания среды собраний, отвечающей вашим требованиям к соответствию. Мы рассмотрим параметры, доступные с метками конфиденциальности и шаблонами, а также способы их использования вместе с другими параметрами администратора Teams.

> [!Note]
> Для параметров собрания в метках конфиденциальности и пользовательских шаблонах собраний требуется Teams премиум.

В этой статье определяются четыре различные конфигурации, начиная с базовой конфигурации для собраний, которые не имеют конкретных требований к соответствию. Каждая дополнительная конфигурация представляет собой значимый шаг в защите, так как параметры собраний становятся все более ограниченными. В конфигурациях, приведенных в этой статье, приведены примеры настройки защиты для собраний с различным уровнем конфиденциальности. Используйте эти примеры, чтобы понять, что возможно, и изменить конкретные параметры по мере необходимости для вашей организации.

Мы обсудим эти три конфигурации:

- Базовая защита

- Защита конфиденциальной информации

- Защита с высоким уровнем конфиденциальности

Кроме того, мы обсудим вариант конфигурации с высокой степенью конфиденциальности, которая предназначена для презентаций с минимальным взаимодействием участников.

## <a name="three-tiers-at-a-glance"></a>Краткий обзор трех уровней

В следующей таблице перечислены конфигурации для каждого уровня. Используйте эти конфигурации в качестве отправной точки и настройте конфигурации в соответствии с потребностями вашей организации. В зависимости от ваших требований к соответствию вам может потребоваться не каждый уровень.

|&nbsp;|Базовой линии|Чувствительной|Высокая степень конфиденциальности|Презентация с высоким уровнем конфиденциальности|
|:-----|:-----|:-----|:-----|:-----|
|Разрешить камеру для участников|**Вкл**|**Вкл**|**Вкл**|**Выкл**|
|Разрешить микрофон для участников|**Вкл**|**Вкл**|**Вкл**|**Выкл**|
|Применение водяного знака к видеопотоку всех пользователей|**Выкл**|**Выкл**|**Вкл**|**Вкл**|
|Применение подложки к общему содержимому|**Выкл**|**Выкл**|**Вкл**|**Вкл**|
|Комплексное шифрование|**Выкл**|**Выкл**|**Вкл**|**Вкл**|
|Управление тем, что видят участники|**Выкл**|**Вкл**|**Вкл**|**Вкл**|
|Чат собрания|**Вкл**|**Вкл**|**Только в собрании**|**Выкл**|
|Люди при звонке в можно обойти лобби|**Выкл**|**Выкл**|**Выкл**|**Выкл**|
|Запрет копирования содержимого чата в буфер обмена|**Выкл**|**Выкл**|**Вкл**|**Вкл**|
|Автоматическая запись|**Выкл**|**Выкл**|**Выкл**|**Выкл**|
|Кто может обойти лобби|**Люди в моей организации, людей в доверенных доменах и гостей**|**Люди я приглашаю**|**Только я и соорганизаторы**|**Только я и соорганизаторы**|
|Кто может представить|**Люди в моей организации и гости**|**Люди в моей организации и гости**|**Только организаторы и соорганизаторы**|**Только организаторы и соорганизаторы**|
|Кто может записывать|**Организаторы и выступающие**|**Организаторы и соорганизаторы**|Отключено из-за подложки|Отключено из-за подложки|

Сведения о настройке каждого уровня рассматриваются в:

- [Настройка собраний Teams с базовой защитой](configure-meetings-baseline-protection.md)
- [Настройка собраний Teams с защитой конфиденциальных данных](configure-meetings-sensitive-protection.md)
- [Настройка собраний Teams с защитой для высоко конфиденциальных данных](configure-meetings-highly-sensitive-protection.md)

## <a name="managing-compliance-with-sensitivity-labels-and-meeting-templates"></a>Управление соответствием с помощью меток конфиденциальности и шаблонов собраний

Шаблоны собраний и метки конфиденциальности могут применять определенные параметры собрания. Большинство параметров можно применить как включено или выключено, либо их можно оставить ненастроенными, чтобы организатор собрания смог их задать.

> [!Important]
> Некоторые функции [управляются политиками администратора](meeting-templates-sensitivity-labels-policies.md#policies-labels-templates-and-meetings-settings) и должны быть включены там, прежде чем они смогут управляться с помощью шаблонов собраний и меток конфиденциальности.

Некоторые параметры доступны только в метках конфиденциальности, а некоторые — только в шаблонах. Доступно несколько вариантов в обоих вариантах:

- Чат
- Комплексное шифрование
- Параметры лобби
- Запись собрания
- Водяных знаков

Метки конфиденциальности и шаблоны можно использовать вместе, чтобы обеспечить соответствие требованиям. Дополнительные сведения см. в статье [Совместное использование шаблонов собраний Teams, меток конфиденциальности и политик администрирования](meeting-templates-sensitivity-labels-policies.md).

## <a name="meeting-chat"></a>Чат собрания

Чат собрания может быть важной частью совместной работы во время собрания. Однако вам может потребоваться ограничить чат собрания в определенных типах собраний, чтобы избежать раскрытия конфиденциальной информации.

Администратор может управлять чатом собраний следующими способами:

- **Политика собраний администратора Teams** (на пользователя или группу) может использоваться для разрешения чата, разрешения чата для всех участников, кроме анонимных участников, или отключения чата.
- **Параметр метки конфиденциальности** (для каждого собрания) может принудительно включить или отключить чат или разрешить его только во время собрания. Этот параметр можно оставить ненастроенным для управления шаблоном или организатором собрания.
- **Параметр шаблона собрания** (для каждого собрания) может принудительно включить или отключить чат или разрешить его только во время собрания. Этот параметр можно оставить ненастроенным для управления организатором собрания.

Для трех уровней защиты мы разрешаем чат для базовых и конфиденциальных собраний и ограничиваем его только собраниями с высоким уровнем конфиденциальности.

Дополнительные сведения см. в разделе [Управление чатом для конфиденциальных собраний Teams](manage-chat-sensitive-meetings.md).

## <a name="meeting-recordings"></a>Записи собраний

Администратор может управлять записями собраний следующими способами:

- Политика собраний администратора **облачной записи** (на пользователя или группу)
- Политика администраторов собраний для собраний **автоматически истекает** (удаление записи) (на пользователя или группу)
- Параметр **"Кто может записывать** " в метках конфиденциальности и шаблонах собраний (на собрание)
- Автоматическое задание **записи** в метках конфиденциальности и шаблонах собраний (на собрание)

Если ваша организация или определенные люди или группы в ней никогда не должны иметь возможность записывать собрания, вы можете отключить эту функцию с помощью политики собраний администратора **облачной записи** .

Если есть определенные типы собраний, которые всегда должны записываться, вы можете применить параметр **Запись автоматически** с помощью шаблона собрания или метки конфиденциальности.

На трех уровнях, рассмотренных здесь, запись отключена на собраниях с высокой степенью конфиденциальности, так как мы используем сквозное шифрование и водяные знаки для общего содержимого и видео. Если вам нужно иметь возможность записывать собрания с высоким уровнем конфиденциальности, убедитесь, что вы не применяете водяные знаки или сквозное шифрование с помощью метки конфиденциальности. Организаторы собраний по-прежнему могут использовать сквозное шифрование и применять водяные знаки, если данное собрание не записывается.

Дополнительные сведения об управлении параметрами записи собраний см. в статье [Управление параметрами записи собраний Microsoft Teams для конфиденциальных собраний](manage-meeting-recording-options.md).

Сведения о записи собраний на основе политик для обеспечения соответствия см. [в статье Общие сведения о записи на основе политик Teams для звонков & собраний](teams-recording-policy.md).

## <a name="meeting-with-guests-and-external-participants"></a>Встреча с гостями и внешними участниками

Есть три типа внешних участников, которые могут присоединиться к собраниям:

- Участники из доверенных доменов
- Гости
- Анонимные участники

Участники из доверенных доменов присоединяются к собраниям с помощью функции [внешнего доступа](manage-external-access.md) . Вы можете контролировать домены , если таковые есть, ваша организация хочет доверять. (Этот параметр также влияет на 1:1 и групповой чат с людьми в этих доменах.)

Если [гостевой доступ Teams](guest-access.md) включен для вашей организации, гости смогут присоединяться к собраниям. Параметры гостевого доступа также можно использовать для управления режимом общего доступа к экрану гостей, включая отключение общего доступа к экрану. (Гостевой доступ также используется для приглашения гостей в команды.)

Если параметр **администратора Teams для анонимных пользователей может присоединиться к собранию** , анонимные участники смогут присоединяться к собраниям.

Хотя анонимное присоединение можно полностью отключить, не затрагивая функции, отличные от собраний, в сценариях за пределами собраний используются как гостевой доступ, так и доверенные домены. Если вы хотите ограничить доступ к собранию для этих участников, но вам нужно оставить включенные функции по другим причинам, необходимо использовать лобби.

## <a name="lobby-options"></a>Варианты лобби

Вестибюль собрания позволяет организаторам собрания проверять участников, прежде чем разрешать им участие в собрании. В зависимости от типа собрания и требований к соответствию требованиям может потребоваться разрешить всем участникам обходить зал ожидания и присоединиться к собранию напрямую или проводить определенные типы участников в зале ожидания, пока они не будут допущены организатором собрания. Если вы хотите запретить посещение собраний определенными типами людей, таких как гости, вы можете заставить их пройти через зал ожидания, а затем организатор собрания может отказать им в приеме.

Для базового уровня мы разрешаем всем, кроме анонимных участников, обходить лобби. Для конфиденциальных собраний мы разрешаем только пользователям с приглашением на собрание обходить зал ожидания. Для собраний с высокой степенью конфиденциальности организаторы должны принимать каждого участника.

Администратор может управлять лобби следующими способами:

- Политика **автоматического допуска к** собраниям администратора пользователей (на пользователя или группу)
- **Пользователи с телефонным подключением могут обходить политику собраний администратора лобби** (на пользователя или группу)
- **Параметр "Кто может обойти лобби**" в метках конфиденциальности и шаблонах собраний (на собрание)
- **Люди набора номера в может обойти** политику собраний администратора лобби (на пользователя или группу) или метки конфиденциальности и шаблоны собраний (на собрание).

Эти параметры также доступны организатору собрания, если они не были заблокированы меткой конфиденциальности или шаблоном.


Хотя политика администратора задает значение по умолчанию, для принудительного применения требуется шаблон или метка.


Если вы находитесь в отрасли с высоким уровнем регулирования и вам нужно вручную допустить каждого участника на все собрания в вашей организации, вы можете настроить лобби с помощью политик собраний администратора в Центре администрирования Teams. Если в вашей организации есть различные типы собраний с разными требованиями к лобби, рекомендуется использовать шаблоны собраний или метки конфиденциальности для настройки этих параметров.

Дополнительные сведения см. [в статье Настройка лобби собраний Microsoft Teams для конфиденциальных собраний](configure-lobby-sensitive-meetings.md).

## <a name="related-topics"></a>См. также

[Иллюстрации Microsoft Cloud для корпоративных архитекторов](/microsoft-365/solutions/cloud-architecture-models)

[Использование меток конфиденциальности для защиты элементов календаря, собраний Teams и чата](/microsoft-365/compliance/sensitivity-labels-meetings)