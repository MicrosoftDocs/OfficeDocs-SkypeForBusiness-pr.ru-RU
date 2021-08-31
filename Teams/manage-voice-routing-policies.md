---
title: Управление политиками маршрутинга голосовой связи для прямой маршрутии
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark
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
description: Узнайте, как создавать политики перенаправки голосовой маршрутики и управлять ими в Microsoft Teams.
ms.openlocfilehash: 1717f1b0400f67346034bd9e92bd698305fdd324
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727098"
---
# <a name="manage-voice-routing-policies-for-direct-routing"></a>Управление политиками маршрутинга голосовой связи для прямой маршрутии

Если в вашей организации развернута прямая маршрут [телефонная система,](direct-routing-landing-page.md) используйте политики маршрутизации голосовой связи, чтобы разрешить пользователям Teams и Skype для бизнеса Online принимать и звонить на телефонную сеть общего пользования (STN) с использованием локальной инфраструктуры телефонии.

Политика голосовой маршрутистики — это контейнер для записей использования ОКП. Чтобы создать политики маршрутинга голосовой маршрутики и управлять ими, переходить к политикам перенаправки голосовой голосовой почты в центре администрирования Microsoft Teams или с помощью   >   Windows PowerShell.

Вы можете использовать глобальную (по умолчанию в пределах организации) политику или создавать и присваивать настраиваемые политики. Пользователи будут автоматически получать глобальную политику, если только вы не создайте и не назначите настраиваемую политику. Имейте в виду, что вы можете изменить параметры глобальной политики, но не можете переименовать или удалить ее.

Важно знать, что назначение пользователю политики голосовой маршрутии не позволяет ему звонить по НН TEAMS. Кроме того, необходимо включить для пользователя прямую маршрутику телефонная система выполнить другие действия по настройке. Дополнительные узнать см. [в настройках прямой маршрутии.](direct-routing-configure.md)

## <a name="create-a-custom-voice-routing-policy"></a>Создание настраиваемой политики маршрутинга голосовой почты

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams перейдите к политике маршрутации голосовой голосовой почты  >  и нажмите кнопку **Добавить**.<br>
    ![Снимок экрана: страница "Добавление политики маршрутинга голосовой почты" в Центре Microsoft Teams администрирования.](media/manage-voice-routing-policies.png) 
2. Введите имя и описание для политики.
3. В **области Записи использования ОКП** щелкните Добавить использование **ПСП** и выберите записи, которые вы хотите добавить. Если вам нужно создать новую запись использования ОКП, нажмите кнопку **Добавить.**
4. Если вы добавили несколько записей использования ОКП, расположить их в нужном порядке.
5. Когда все будет готово, нажмите кнопку **Применить**.
6. Нажмите кнопку **Сохранить**.

### <a name="using-powershell"></a>С помощью PowerShell

См. [new-CsOnlineVoiceRoutingPolicy.](/powershell/module/skype/new-csonlinevoiceroutingpolicy)

## <a name="edit-a-voice-routing-policy"></a>Изменение политики маршрутики голосовой почты

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

Вы можете редактировать глобальную политику или любые настраиваемые политики, которые вы создаете.

1. В левой области навигации Центра администрирования Microsoft Teams перейдите **к** политике маршрутации  >  **голосовой голосовой почты.**
2. Выберите политику, щелкнув слева от ее имени, а затем нажмите **Изменить**.
3. Щелкните **Добавить/удалить записи** использования ОКП , внести нужные изменения и нажмите кнопку **Сохранить**.

### <a name="using-powershell"></a>С помощью PowerShell

См. [set-CsOnlineVoiceRoutingPolicy.](/powershell/module/skype/set-csonlinevoiceroutingpolicy)

## <a name="assign-a-custom-voice-routing-policy-to-users"></a>Назначение пользовательской политики маршрутинга голосовой почты пользователям

[!INCLUDE [assign-policy](includes/assign-policy.md)]

См. [также Grant-CsOnlineVoiceRoutingPolicy.](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)

## <a name="related-topics"></a>Статьи по теме

[Обзор PowerShell в Teams](teams-powershell-overview.md)

[Настройка голосовой маршрутии для прямой маршрутии](direct-routing-voice-routing.md)

[Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации](location-based-routing-enable.md)

[Назначение политик пользователям в Teams](assign-policies.md)