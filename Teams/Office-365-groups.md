---
title: Группы Microsoft 365 и Microsoft Teams
ms.reviewer: kblevins
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: Узнайте, как группы Microsoft 365 и членство в группах работают с Microsoft Teams.
ms.openlocfilehash: d258fa4252f6bbb02d2b9a8211dd5919c2d7a67b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105245"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Группы Microsoft 365 и Microsoft Teams

Группы Microsoft 365 — это служба, в составная служба для перекрестных приложений Microsoft 365. На базовом уровне группа Microsoft 365 — это объект в Azure Active Directory со списком участников и списком связанных рабочих нагрузок, включая сайт группы SharePoint, общий почтовый ящик Exchange, Планировщик и рабочая область Power BI. Вы можете добавлять и удалять людей в группе, как и любые другие объекты безопасности на основе группы в Active Directory.

![Схема, показывающая Группы Microsoft 365 и связанные службы](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

По умолчанию пользователи в Microsoft 365 могут создавать группы и управлять ими. Дополнительные сведения о Группах Microsoft 365 см. в плакате "Группы [Microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) и Группы [в Microsoft 365 для ИТ-архитекторов".](teams-architecture-solutions-posters.md#groups-in-microsoft-365)

## <a name="how-microsoft-365-groups-work-with-teams"></a>Работа групп Microsoft 365 с Teams

При создании команды создается группа Microsoft 365, которая будет управлять членством в них. Связанные службы группы, такие как сайт SharePoint, рабочая область Power BI и т. д., создаются одновременно.

Люди, которые создают команды, могут использовать существующую группу Microsoft 365, если они являются ее владельцем. У каждого канала команды есть отдельная папка в библиотеке документов. При создании папок непосредственно в библиотеке документов каналы в команде не создаются.

При создании группы Microsoft 365 в Outlook или SharePoint почтовый ящик группы отображается в Outlook. При создании команды в Teams почтовый ящик группы по умолчанию скрыт. Чтобы сделать почтовый ящик видимым, можно использовать cmdlet [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) с параметром **HiddenFromExchangeClientsEnabled.**

## <a name="group-membership"></a>Членство в группах

При удалении участника команды он также удаляется из группы Microsoft 365. При удалении из группы сразу же удаляются команда и каналы из клиента Teams. Если удалить человека из группы с помощью Центра администрирования Microsoft 365, у него больше не будет доступа к другим аспектам совместной работы, таким как библиотека документов SharePoint Online, группа Yammer или общий доступ к OneNote. Однако у него по-прежнему будет доступ к функциям чата группы в течение приблизительно двух часов.

Чтобы обеспечить быстрое обновление разрешений для других подключенных к группе рабочих нагрузок, добавьте их в клиент Teams и удалите из него. Если вы добавите или удалите участников команды за пределами клиента Teams (с помощью Центра администрирования Microsoft 365, Azure AD или Exchange Online PowerShell), для отражения изменений в Teams может занять до 24 часов.

## <a name="deleting-groups-and-teams"></a>Удаление групп и групп

При удалении группы Microsoft 365 удаляется псевдоним почтового ящика для сохраняемой беседы Outlook/OWA и приглашения на собрания Teams, а сайт SharePoint пометка для удаления. Удаление команды и ее действие в Outlook занимает около 20 минут. При удалении команды из клиента Teams она сразу же удаляется из представления для всех участников команды. При удалении участников группы Microsoft 365, для которых были включены функции Teams, в течение приблизительно двух часов команда может быть удалена из представления в клиенте Teams для затронутых людей.

Подробные сведения о параметрах окончания жизненного цикла групп и команд см. в параметрах окончания жизненного цикла [групп, групп, Yammer](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) и архива либо удаления команды [в Microsoft Teams.](./archive-or-delete-a-team.md)

## <a name="related-topics"></a>Статьи по теме

[Основы Microsoft Teams (видео)](https://aka.ms/teams-foundations)

[Восстановление удаленной группы](/microsoft-365/admin/create-groups/restore-deleted-group)