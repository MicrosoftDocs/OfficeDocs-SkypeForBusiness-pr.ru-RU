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
description: Узнайте, как использовать политики команд и управлять ими в организации, чтобы контролировать то, что пользователи могут делать в командах и каналах.
ms.openlocfilehash: 81541c08ac963f0bcef18ba589b2341915c20d5d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094209"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>Управление политиками команд в Microsoft Teams

Как администратор вы можете использовать политики teams в Microsoft Teams для управления тем, что пользователи в вашей организации могут делать в командах и каналах. Например, можно разрешить пользователям создавать частные каналы.

Вы управляете политиками **команд,** переходить к политикам Teams  >  **в** Центре администрирования Microsoft Teams. Вы можете использовать глобальную (по умолчанию в пределах организации) политику или создавать и присваивать настраиваемые политики. Пользователи вашей организации автоматически получают глобальную политику, если вы не создали и не назначили настраиваемую политику.

Вы можете изменить глобальную политику или создать и назначить настраиваемую политику. После изменения глобальной политики или назначения политики может занять несколько часов, чтобы изменения вступили в силу.

## <a name="create-a-custom-teams-policy"></a>Создание настраиваемой политики teams

1. В левой области навигации Центра администрирования Microsoft Teams перейдите к политикам **Teams.**  >  
2. Нажмите **Добавить**.
3. Введите имя и описание для политики.

    ![Снимок экрана: параметры политики Teams](media/teams-policies.png)
4. Включите или **отключите** <a name="createchannels"></a> создание частных каналов в зависимости от того, хотите ли вы разрешить пользователям создавать частные каналы.

5. Нажмите кнопку **Сохранить**.

## <a name="edit-a-teams-policy"></a>Изменение политики teams

Вы можете изменить глобальную политику или любые настраиваемые политики, которые вы создаете.

1. В левой области навигации Центра администрирования Microsoft Teams перейдите к политикам **Teams.**  >  
2. Выберите политику, щелкнув слева от ее имени, а затем нажмите **Изменить**.
3. Включите или отключите нужные параметры, а затем нажмите кнопку **"Сохранить".**

## <a name="assign-a-custom-teams-policy-to-users"></a>Назначение настраиваемой политики команд пользователям

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Статьи по теме

[Закрытые каналы в Teams](private-channels.md)

[Назначение политик пользователям в Teams](assign-policies.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)