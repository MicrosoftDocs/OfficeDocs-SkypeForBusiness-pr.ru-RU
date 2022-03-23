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
ms.openlocfilehash: 5acac362485b1004e1db61229c437810fdbcbc6d
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711783"
---
# <a name="manage-channel-policies-in-microsoft-teams"></a>Управление политиками каналов в Microsoft Teams

Как администратор вы можете использовать политики в Microsoft Teams для управления тем, что пользователи в организации могут делать в командах и каналах. Например, можно у установить, разрешено ли пользователям создавать частные или общие каналы.

Вы управляете политиками команд, **Teams** >  **Teams политики** в Microsoft Teams администрирования. Вы можете использовать глобальную (по умолчанию в пределах организации) политику или создавать и присваивать настраиваемые политики. Пользователи вашей организации автоматически получают глобальную политику, если вы не создали и не назначили настраиваемую политику.

Вы можете изменить глобальную политику или создать и назначить настраиваемую политику. После изменения глобальной политики или назначения политики может потребоваться 24 часа, чтобы изменения вступили в силу.

## <a name="channel-policies"></a>Политики каналов

Для каналов teams доступны следующие политики:

|Политика|Описание|
|:-----|:----------|
|**Создание частных каналов**|В **этом случае** владельцы и участники команды могут создавать частные каналы. (Владельцы команд могут управлять тем, могут ли участники создавать частные каналы в каждой команде.)|
|**Создание общих каналов**|В **этом случае** владельцы команд могут создавать общие каналы. Teams приложения, доступные в вашей организации, также доступны в общих каналах.|
|**Приглашение внешних пользователей в общие каналы**|В **этом случае** владельцы и участники общих каналов могут приглашать внешних участников из организаций, в которых настроено доверие между организациями. Teams политики организации применяются к этим каналам.|
|**Присоединяйтесь к внешним общим каналам**|В **этом случае** пользователи могут участвовать в общих каналах, созданных другими организациями, в которых настроено доверие между организациями. Teams политики для другой организации применяются к этим каналам.|

## <a name="create-a-custom-teams-policy"></a>Создание настраиваемой политики teams

1. В левой области навигации центра администрирования Microsoft Teams перейдите **к Teams** >  **Teams политики**.
2. Нажмите **Добавить**.
3. Введите имя и описание для политики.

    ![Снимок экрана: параметры политики teams.](media/teams-policies.png)
4. Включите или отключите нужные параметры, а затем нажмите кнопку **Сохранить**.

5. Нажмите кнопку **Сохранить**.

## <a name="edit-a-teams-policy"></a>Изменение политики teams

Вы можете изменить глобальную политику или любые настраиваемые политики, которые вы создаете.

1. В левой области навигации центра администрирования Microsoft Teams перейдите **к Teams** >  **Teams политики**.
2. Выберите политику, щелкнув слева от ее имени, а затем нажмите **Изменить**.
3. Включите или отключите нужные параметры, а затем нажмите кнопку **Сохранить**.

## <a name="assign-a-custom-teams-policy-to-users"></a>Назначение настраиваемой политики teams пользователям

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>См. также

[Управление Teams подключенными сайтами и сайтами каналов](/SharePoint/teams-connected-sites)

[Частные каналы в Teams](private-channels.md)

[Назначение политик пользователям в Teams](policy-assignment-overview.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy)
