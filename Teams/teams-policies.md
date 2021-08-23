---
title: Управление политиками команд в Microsoft Teams
author: cichur
ms.author: v-cichur
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
description: Узнайте, как использовать политики команд в организации и управлять ими, чтобы контролировать то, что пользователи могут делать в командах и каналах.
ms.openlocfilehash: 4f5c8e638b5166c15223f0aee0034f1b18743bcf
ms.sourcegitcommit: 85017cf88789c750836780dad2ef707c1c6c39b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/16/2021
ms.locfileid: "58359156"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>Управление политиками команд в Microsoft Teams

Как администратор вы можете использовать политики teams в Microsoft Teams для управления тем, что пользователи в организации могут делать в командах и каналах. Например, вы можете разрешить пользователям создавать частные каналы.

Вы управляете политиками команд, **Teams**  >  **Teams политики** в Microsoft Teams администрирования. Вы можете использовать глобальную (по умолчанию в пределах организации) политику или создавать и присваивать настраиваемые политики. Пользователи вашей организации автоматически получают глобальную политику, если вы не создали и не назначили настраиваемую политику.

Вы можете изменить глобальную политику или создать и назначить настраиваемую политику. После изменения глобальной политики или назначения политики может занять несколько часов, чтобы изменения вступили в силу.

## <a name="create-a-custom-teams-policy"></a>Создание настраиваемой политики teams

1. В левой области навигации Центра Microsoft Teams администрирования перейдите к **Teams**  >  **Teams политики**.
2. Нажмите **Добавить**.
3. Введите имя и описание для политики.

    ![Снимок экрана: параметры политики teams](media/teams-policies.png)
4. Включите или отключите <a name="createchannels"></a> **создание** частных каналов в зависимости от того, хотите ли вы разрешить пользователям создавать частные каналы.

5. Нажмите кнопку **Сохранить**.

## <a name="edit-a-teams-policy"></a>Изменение политики teams

Вы можете редактировать глобальную политику или любые настраиваемые политики, которые вы создаете.

1. В левой области навигации Центра Microsoft Teams администрирования перейдите к **Teams**  >  **Teams политики**.
2. Выберите политику, щелкнув слева от ее имени, а затем нажмите **Изменить**.
3. Включите или отключите нужные параметры, а затем нажмите кнопку **Сохранить**.

## <a name="assign-a-custom-teams-policy-to-users"></a>Назначение настраиваемой политики teams пользователям

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Связанные статьи

[Управление Teams подключенными сайтами и сайтами каналов](/SharePoint/teams-connected-sites)

[Закрытые каналы в Teams](private-channels.md)

[Назначение политик пользователям в Teams](assign-policies.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)
