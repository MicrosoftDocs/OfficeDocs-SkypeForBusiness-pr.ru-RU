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
description: Узнайте, как использовать политики каналов teams в организации и управлять ими, чтобы контролировать то, что пользователи могут делать в командах и каналах.
ms.openlocfilehash: 727bb8b133d5119cd396c79561dde453281206f0
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432271"
---
# <a name="manage-channel-policies-in-microsoft-teams"></a>Управление политиками каналов в Microsoft Teams

Как администратор вы можете использовать политики команд в Microsoft Teams управлять тем, что пользователи в вашей организации могут делать в командах и каналах. Например, вы можете разрешить пользователям создавать частные каналы.

Вы управляете политиками команд, **Teams**  >  **Teams политики** в Microsoft Teams администрирования. Вы можете использовать глобальную (по умолчанию в пределах организации) политику или создавать и присваивать настраиваемые политики. Пользователи вашей организации автоматически получают глобальную политику, если вы не создали и не назначили настраиваемую политику.

Вы можете изменить глобальную политику или создать и назначить настраиваемую политику. После изменения глобальной политики или назначения политики может занять несколько часов, чтобы изменения вступили в силу.

## <a name="create-a-custom-teams-policy"></a>Создание настраиваемой политики teams

1. В левой области навигации Центра Microsoft Teams администрирования перейдите к **Teams**  >  **Teams политики**.
2. Нажмите **Добавить**.
3. Введите имя и описание для политики.

    ![Снимок экрана: параметры политики teams.](media/teams-policies.png)
4. Включите или отключите <a name="createchannels"></a> **создание** частных каналов в зависимости от того, хотите ли вы разрешить пользователям создавать частные каналы.

5. Нажмите кнопку **Сохранить**.

## <a name="edit-a-teams-policy"></a>Изменение политики teams

Вы можете изменить глобальную политику или любые настраиваемые политики, которые вы создаете.

1. В левой области навигации Центра Microsoft Teams администрирования перейдите к **Teams**  >  **Teams политики**.
2. Выберите политику, щелкнув слева от ее имени, а затем нажмите **Изменить**.
3. Включите или отключите нужные параметры, а затем нажмите кнопку **Сохранить**.

## <a name="assign-a-custom-teams-policy-to-users"></a>Назначение настраиваемой политики teams пользователям

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Статьи по теме

[Управление Teams подключенными сайтами и сайтами каналов](/SharePoint/teams-connected-sites)

[Частные каналы в Teams](private-channels.md)

[Назначение политик пользователям в Teams](assign-policies.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)
