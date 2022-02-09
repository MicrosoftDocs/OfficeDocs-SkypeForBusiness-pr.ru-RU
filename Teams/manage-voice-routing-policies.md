---
title: Управление политиками маршрутинга  вызовов для прямой маршрутизы
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: filippse
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Узнайте, как создавать политики маршрутинга  вызовов и управлять ими Microsoft Teams прямой маршрутии.
ms.openlocfilehash: 348eef9e33dba4f33868c94d72e21289b1a87690
ms.sourcegitcommit: 79dfda39db208cf943d0f7b4906883bb9d034281
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2022
ms.locfileid: "62457399"
---
# <a name="manage-call-routing-policies-for-direct-routing"></a>Управление политиками маршрутинга  вызовов для прямой маршрутизы

Если вы развернули прямую [](direct-routing-landing-page.md) маршрутику в организации, с помощью политик маршрутизации звонков можно разрешить пользователям Teams принимать и звонить на телефонную сеть общего пользования с использованием локальной инфраструктуры телефонной сети.

Политика маршрутизов  вызовов (также называемая политикой голосовой маршрутии) является контейнером для записей использования ОКП. Чтобы создать политики маршрутики голосовой маршрутики и управлять ими, переходить к политикам маршрутики **VoiceVoice**  >  в центре администрирования Microsoft Teams или с помощью Windows PowerShell.

Вы можете использовать глобальную (по умолчанию в пределах организации) политику или создавать и присваивать настраиваемые политики. Пользователи будут автоматически получать глобальную политику, если только вы не создайте и не назначите настраиваемую политику. Имейте в виду, что вы можете изменить параметры глобальной политики, но не можете переименовать или удалить ее.

Важно знать, что назначение пользователю политики голосовой маршрутии не позволяет ему звонить по НН TEAMS. Кроме того, необходимо включить прямую маршрутику для пользователя и выполнить другие действия по настройке. Дополнительные узнать об этом см [. в этой ссылке](direct-routing-configure.md).

## <a name="create-a-custom-call-routing-policy"></a>Создание настраиваемой политики маршрутизов  вызовов

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации центра Microsoft Teams перейдите к центру **политики** маршрутации **VoiceVoice** >  и нажмите кнопку **Добавить**.<br>

2. Введите имя и описание для политики.

3. В **области Записи использования** ННР щелкните Добавить использование ННР **, а** затем выберите записи, которые вы хотите добавить. Если вам нужно создать новую запись использования ОКП, нажмите кнопку **Добавить**.

4. Если вы добавили несколько записей использования ОКП, расположить их в нужном порядке.
5. Когда все будет готово, нажмите кнопку **Применить**.

6. Нажмите кнопку **Сохранить**.

### <a name="using-powershell"></a>С помощью PowerShell

См [. new-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy).

## <a name="edit-a-call-routing-policy"></a>Изменение политики маршрутизов  вызовов

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

Вы можете изменить глобальную политику или любые настраиваемые политики, которые вы создаете.

1. В левой области навигации центра Microsoft Teams перейдите к политикам **маршрутации VoiceVoice** > .

2. Выберите политику, щелкнув слева от ее имени, а затем нажмите **Изменить**.

3. Нажмите **кнопку Добавить/удалить** записи использования ОКП, внести нужные изменения и нажмите кнопку **Сохранить**.

### <a name="using-powershell"></a>С помощью PowerShell

См [. set-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/set-csonlinevoiceroutingpolicy).

## <a name="assign-a-custom-call-routing-policy-to-users"></a>Назначение пользовательской политики маршрутизов пользователям

[!INCLUDE [assign-policy](includes/assign-policy.md)]

См. [также Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy).

## <a name="related-topics"></a>Статьи по теме

[Обзор PowerShell в Teams](teams-powershell-overview.md)

[Настройка маршрутизов  вызовов для прямой маршрутии](direct-routing-voice-routing.md)

[Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации](location-based-routing-enable.md)

[Назначение политик пользователям в Teams](policy-assignment-overview.md)