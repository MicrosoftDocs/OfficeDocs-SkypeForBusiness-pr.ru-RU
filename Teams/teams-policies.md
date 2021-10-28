---
title: Управление политиками каналов в Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
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
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
description: Узнайте, как использовать политики каналов teams и управлять ими в организации, чтобы контролировать то, что пользователи могут делать в командах и каналах.
ms.openlocfilehash: 787978d6863a66b39c75f3f2c7315fe1495730c3
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605615"
---
# <a name="manage-channel-policies-in-microsoft-teams"></a>Управление политиками каналов в Microsoft Teams

Как администратор вы можете использовать политики команд в Microsoft Teams управлять тем, что пользователи в вашей организации могут делать в командах и каналах. Например, вы можете разрешить пользователям создавать частные каналы.

Вы управляете политиками команд, **Teams** Teams политики в  >   Microsoft Teams администрирования. Вы можете использовать глобальную (по умолчанию в пределах организации) политику или создавать и присваивать настраиваемые политики. Пользователи вашей организации автоматически получают глобальную политику, если вы не создали и не назначили настраиваемую политику.

Вы можете изменить глобальную политику или создать и назначить настраиваемую политику. После изменения глобальной политики или назначения политики может занять несколько часов, чтобы изменения вступили в силу.

## <a name="create-a-custom-teams-policy"></a>Создание настраиваемой политики teams

1. В левой области навигации Центра администрирования Microsoft Teams перейдите к **Teams**  >  **Teams политики**.
2. Нажмите **Добавить**.
3. Введите имя и описание для политики.

    ![Снимок экрана: параметры политики teams.](media/teams-policies.png)
4. Включите или отключите <a name="createchannels"></a> **создание** частных каналов в зависимости от того, хотите ли вы разрешить пользователям создавать частные каналы.

5. Нажмите кнопку **Сохранить**.

## <a name="edit-a-teams-policy"></a>Изменение политики teams

Вы можете редактировать глобальную политику или любые настраиваемые политики, которые вы создаете.

1. В левой области навигации Центра администрирования Microsoft Teams перейдите к **Teams**  >  **Teams политики**.
2. Выберите политику, щелкнув слева от ее имени, а затем нажмите **Изменить**.
3. Включите или отключите нужные параметры, а затем нажмите кнопку **Сохранить**.

## <a name="assign-a-custom-teams-policy-to-users"></a>Назначение настраиваемой политики teams пользователям

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Статьи по теме

[Управление Teams подключенными сайтами и сайтами каналов](/SharePoint/teams-connected-sites)

[Закрытые каналы в Teams](private-channels.md)

[Назначение политик пользователям в Teams](policy-assignment-overview.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy)
