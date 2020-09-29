---
title: Управление политиками Teams в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Сведения о том, как использовать политики Teams в Организации и управлять ими, чтобы управлять тем, какие пользователи могут выполнять в Teams и каналах.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: ad7dadc60b1fb53a518ec5cab340739a89f6b044
ms.sourcegitcommit: 6f4928e9e7e67fe65320131ae9e7348b948d86ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "48297381"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>Управление политиками Teams в Microsoft Teams

Администраторы могут использовать политики Teams в Microsoft Teams для управления тем, какие пользователи в организации могут выполнять в Teams и каналах. Например, вы можете указать, разрешено ли пользователям создавать закрытые каналы.

Управление политиками Teams осуществляется путем **перехода в**  >  **политики** Teams в центре администрирования Microsoft Teams. Вы можете использовать глобальную политику (по умолчанию на уровне Организации) или создавать и назначать пользовательские политики. Пользователи вашей организации автоматически получают глобальную политику, если вы не создали и не назначили настраиваемую политику.

Вы можете изменять глобальную политику или создавать и назначать пользовательские политики. После изменения глобальной политики или назначения политики может потребоваться несколько часов, чтобы изменения вступили в силу.

## <a name="create-a-custom-teams-policy"></a>Создание настраиваемой политики рабочих групп

1. В левой области навигации центра администрирования Microsoft Teams перейдите в раздел политики **Teams**Teams  >  **Teams policies**.
2. Нажмите **Добавить**.
3. Введите имя и описание для политики.

    ![Снимок экрана: параметры политики Teams](media/teams-policies.png)
4. Включите или отключите функцию **создания частных каналов**в зависимости <a name="createchannels"> </a> от того, хотите ли вы разрешить пользователям создавать закрытые каналы.

5. Нажмите кнопку **Сохранить**.

## <a name="edit-a-teams-policy"></a>Изменение политики Teams

Вы можете изменить глобальную политику или созданные вами пользовательские политики.

1. В левой области навигации центра администрирования Microsoft Teams перейдите в раздел политики **Teams**Teams  >  **Teams policies**.
2. Выберите политику, щелкнув слева от ее имени, а затем нажмите кнопку **изменить**.
3. Включите или выключите нужные параметры, а затем нажмите кнопку **сохранить**.

## <a name="assign-a-custom-teams-policy-to-users"></a>Назначение пользователям политики групп

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Связанные статьи

[Личные каналы в Teams](private-channels.md)

[Назначение политик пользователям в Teams](assign-policies.md)
