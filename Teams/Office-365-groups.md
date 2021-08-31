---
title: Microsoft 365 Группы и Microsoft Teams
ms.reviewer: kblevins
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: Узнайте, как Microsoft 365 и членство в группах с Microsoft Teams.
ms.openlocfilehash: 4e140d50bb16c9ed99f126662545fb026c3df60a
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729738"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 Группы и Microsoft Teams

Microsoft 365 Groups — это служба, в составной Microsoft 365. На базовом уровне группа Microsoft 365 — это объект в Azure Active Directory со списком участников и связанными рабочими нагрузками, включая сайт группы SharePoint, общий почтовый ящик Exchange, Планировщик и рабочая область Power BI. В группу можно добавлять и удалять пользователей так же, как и любые другие объекты безопасности на основе группы в Active Directory.

![Схема, показывающая Microsoft 365 групп и связанных служб.](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

По умолчанию пользователи в Microsoft 365 могут создавать группы и управлять ими. Дополнительные сведения о группах Microsoft 365 см. в Microsoft 365 [группах](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) и группах Microsoft 365 для [ИТ-архитекторов.](teams-architecture-solutions-posters.md#groups-in-microsoft-365)

## <a name="how-microsoft-365-groups-work-with-teams"></a>Как Microsoft 365 группы работают с Teams

При создании команды создается Microsoft 365 для управления членством в них. Одновременно создаются связанные службы группы, например сайт SharePoint, Power BI рабочей области и т. д.

Люди, которые создают команды, могут использовать существующую группу Microsoft 365, если они являются ее владельцем. У каждого канала группы есть отдельная папка в библиотеке документов. При создании папок непосредственно в библиотеке документов каналы в группе не создаются.

При создании группы Microsoft 365 в Outlook или SharePoint, почтовый ящик группы отображается в Outlook. При создании группы в Teams почтовый ящик группы по умолчанию скрыт. Чтобы сделать почтовый ящик видимым, можно использовать параметр [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) с параметром **HiddenFromExchangeClientsEnabled.**

## <a name="group-membership"></a>Членство в группах

При удалении участника команды он также удаляется из Microsoft 365 группы. Удаление из группы немедленно удаляет группу и каналы из Teams клиента. Если удалить человека из группы с помощью Центр администрирования Microsoft 365, он больше не будет иметь доступа к другим аспектам совместной работы, таким как библиотека документов SharePoint Online, группа Yammer или общий доступ OneNote. Однако у него по-прежнему будет доступ к функциям чата группы в течение примерно двух часов.

Чтобы обеспечить быстрое обновление разрешений для других подключенных к группе рабочих нагрузок, добавьте их в клиент Teams и удалите из него. Если вы добавляете или удаляете участников группы за пределами клиента Teams (с помощью Центр администрирования Microsoft 365, Azure AD или Exchange Online PowerShell), на их отражение в Teams может быть до 24 часов.

## <a name="deleting-groups-and-teams"></a>Удаление групп и команд

При удалении Microsoft 365 группы удаляются псевдонимы почтовых ящиков для бесед Outlook/OWA и Teams приглашений на собрания, а также пометка сайта SharePoint для удаления. Удаление команды и ее влияние на удаление команды занимает около 20 Outlook. Удаление команды из клиента Teams сразу же удаляет ее из представления для всех участников группы. При удалении участников группы Microsoft 365, для которых включена функциональность Teams, может быть около двух часов, прежде чем группа будет удалена из представления в клиенте Teams для затронутых людей, которые были удалены.

Подробные сведения о группах и вариантах окончания жизненного цикла групп см. в параметрах окончания жизненного цикла [групп,](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) групп и Yammer и Архивировать или удалить команду в [Microsoft Teams.](./archive-or-delete-a-team.md)

## <a name="related-topics"></a>Статьи по теме

[Основы Microsoft Teams (видео)](https://aka.ms/teams-foundations)

[Восстановление удаленной группы](/microsoft-365/admin/create-groups/restore-deleted-group)