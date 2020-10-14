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
description: Узнайте о том, как в Microsoft Teams можно работать с группами и участием групп Microsoft 365.
ms.openlocfilehash: a4227432ab3557ca5e74ee5a769641185c1e432c
ms.sourcegitcommit: f18941b6dc17b6ea411e10970602aee271242d43
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456083"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Группы Microsoft 365 и Microsoft Teams

Microsoft 365 Groups — это служба членства в разных приложениях в Microsoft 365. На базовом уровне группа Microsoft 365 — это объект в Azure Active Directory со списком участников и связанной рабочей нагрузкой, включая сайт группы SharePoint, общий почтовый ящик Exchange, планировщик и рабочую область Power BI. Вы можете добавлять и удалять пользователей в группе так же, как и любые другие объекты безопасности на основе группы в Active Directory.

![Схема, на которой показаны группы Microsoft 365 и связанные службы](https://docs.microsoft.com/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

По умолчанию пользователи в Microsoft 365 могут создавать группы и управлять ими. Дополнительные сведения о группах Microsoft 365 можно найти в [статье сведения 365 о группах](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) и [группах в Microsoft 365 для плакатов для ИТ – архитекторов](teams-architecture-solutions-posters.md#groups-in-microsoft-365) .

## <a name="how-microsoft-365-groups-work-with-teams"></a>Принципы работы групп Microsoft 365 с Teams

При создании команды создается группа Microsoft 365, с помощью которой можно управлять членством в группе. Связанные с группой службы, такие как сайт SharePoint, Рабочая область Power BI и т. д., создаются одновременно.

Пользователи, которые создают группы, могут использовать существующую группу Microsoft 365, если они являются владельцами этой группы. Каждый канал в группе содержит отдельную папку в библиотеке документов. Создание папок непосредственно в библиотеке документов не приводит к созданию каналов в команде.

При создании группы Microsoft 365 в Outlook или SharePoint групповой почтовый ящик отображается в Outlook. При создании группы в Teams почтовый ящик группы по умолчанию скрыт. Вы можете использовать командлет [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup) с параметром **HiddenFromExchangeClientsEnabled** , чтобы сделать почтовый ящик видимым.

## <a name="group-membership"></a>Членство в группах

Если вы удалите участника команды, он также будет удален из группы Microsoft 365. Удаление из группы немедленно удаляет группу и каналы из клиента Teams. Если вы удалили человека из группы с помощью центра администрирования Microsoft 365, у него больше не будет доступа к другим аспектам совместной работы, таким как библиотека документов SharePoint Online, Группа Yammer или общая программа OneNote. Однако они по-прежнему смогут получать доступ к функциям чата для участников группы в течение примерно двух часов.

В качестве рекомендации по управлению участниками группы добавьте и удалите их из клиента Teams, чтобы убедиться в том, что обновления разрешений для других рабочих нагрузок, подключенных к группам, выполняются быстро. Если вы добавляете или удаляете участников группы за пределами клиента Teams (с помощью центра администрирования Microsoft 365, Azure AD или Exchange Online PowerShell), это может занять до 24 часов, чтобы изменения были отражены в Teams.

## <a name="deleting-groups-and-teams"></a>Удаление групп и команд

Удаление группы Microsoft 365 приведет к удалению псевдонима почтового ящика для постоянных разговоров Outlook/OWA и приглашений на собрание Teams и пометке сайта SharePoint для удаления. Удаление команды и ее воздействия на Outlook занимает около 20 минут. Удаление команды из клиента Teams немедленно удалит ее из представления всем пользователям, которые являются участниками команды. Если удалить пользователей из группы Microsoft 365, на которых включены функции Teams, может быть задержка около двух часов перед тем, как команда будет удалена из представления в клиенте Teams для уязвимых пользователей, которые были удалены.

Сведения о завершении параметров жизненного цикла групп и Teams можно найти в разделе  [Параметры жизненного цикла для групп, Teams, Yammer](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) и [Архивация или удаление группы в Microsoft Teams](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team).

## <a name="related-topics"></a>Статьи по теме

[Основы Microsoft Teams (видео)](https://aka.ms/teams-foundations)

[Восстановление удаленной группы](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)