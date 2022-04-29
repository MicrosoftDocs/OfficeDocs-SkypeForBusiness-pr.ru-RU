---
title: Группы Microsoft 365 и Microsoft Teams
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
description: Узнайте, как Microsoft 365 группы и членство в группах работают с Microsoft Teams.
ms.openlocfilehash: cf84c58e05e65b187ebe9c0d5a4560cf861fb9be
ms.sourcegitcommit: d16fb01f752d186445893ea8e3b0d4450a4a0e67
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2022
ms.locfileid: "65125434"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Группы Microsoft 365 и Microsoft Teams

Группы Microsoft 365 является службой членства между приложениями в Microsoft 365. На базовом уровне группа Microsoft 365 — это объект в Azure Active Directory со списком участников и связью со связанными рабочими нагрузками, включая сайт группы SharePoint, общий почтовый ящик Exchange, Планировщик и записную книжку OneNote. Вы можете добавлять или удалять людей в группу так же, как и любой другой объект безопасности на основе группы в Active Directory.

![Схема, на Группы Microsoft 365 и связанных службах.](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

По умолчанию пользователи в Microsoft 365 могут создавать группы и управлять ими. Дополнительные сведения о Группы Microsoft 365 см. в статье [Группы Microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) о группах в [Microsoft 365 для ИТ-архитекторов](teams-architecture-solutions-posters.md#groups-in-microsoft-365).

## <a name="how-microsoft-365-groups-work-with-teams"></a>Как Группы Microsoft 365 с Teams

При создании команды создается Microsoft 365 для управления членством в команде. Связанные службы группы, такие как сайт SharePoint, почтовый ящик и т. д., создаются одновременно.

Пользователи, которые создают команды, могут использовать существующую группу Microsoft 365, если они являются ее владельцем. Каждый канал в команде имеет отдельную папку в библиотеке документов. Создание папок непосредственно в библиотеке документов не приводит к созданию каналов в команде.

При создании Microsoft 365 в Outlook или SharePoint почтовый ящик группы отображается в Outlook. При создании команды в Teams почтовый ящик группы по умолчанию скрыт. Чтобы сделать почтовый ящик видимым, можно использовать командлет [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) с параметром **HiddenFromExchangeClientsEnabled** .

## <a name="group-membership"></a>Членство в группах

Если удалить участника команды, он также будет удален из Microsoft 365 группы. Удаление из группы немедленно удаляет команду и каналы из Teams клиента. Если удалить пользователя из группы с помощью Центр администрирования Microsoft 365, он больше не будет иметь доступа к другим аспектам совместной работы, таким как библиотека документов SharePoint Online, Yammer группа или общие OneNote. Однако у них по-прежнему будет доступ к функциям чата команды в течение примерно двух часов.

Рекомендуется для управления членами команды добавлять и удалять их из клиента Teams, чтобы обеспечить быстрое обновление разрешений для других рабочих нагрузок, подключенных к группе. При добавлении или удалении участников команды за пределами клиента Teams (с помощью Центр администрирования Microsoft 365, Azure AD или Exchange Online PowerShell) может потребоваться до 24 часов для отражения изменений в Teams.

## <a name="deleting-groups-and-teams"></a>Удаление групп и команд

При удалении группы Microsoft 365 будет удален псевдоним почтового ящика для постоянных бесед Outlook/OWA и Teams приглашений на собрание, а также пометка сайта SharePoint для удаления. Удаление команды и ее влияние на Outlook занимает около 20 минут. При удалении команды из Teams клиент немедленно удаляет ее из представления для всех участников команды. При удалении участников группы Microsoft 365 с включенной Teams включенной функцией может потребоваться около двух часов, прежде чем команда будет удалена из представления в клиенте Teams для затронутых пользователей, которые были удалены.

Дополнительные сведения о вариантах окончания жизненного цикла групп и команд см. в разделе "Параметры окончания жизненного цикла групп, команд и [Yammer](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) и архивации или удаления команды в [Microsoft Teams".](./archive-or-delete-a-team.md)

## <a name="related-topics"></a>Статьи по теме

[Основы Microsoft Teams (видео)](https://aka.ms/teams-foundations)

[Восстановление удаленной группы](/microsoft-365/admin/create-groups/restore-deleted-group)
