---
title: Поиск событий Microsoft Teams в журнале аудита
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Узнайте, как извлекать данные Microsoft Teams из журнала аудита Office 365.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3d6b0ddd0dc5064d484c8420b42daee1b4e16d0e
ms.sourcegitcommit: 5ec5df597614d402917e0585575dd69acda22172
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2019
ms.locfileid: "36253904"
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Поиск событий Microsoft Teams в журнале аудита
==================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Журнал аудита помогает анализировать определенные действия в службах Office 365. Примеры таких действий в Teams.

-   Создание команды

-   Удаление команды

-   Добавление канала

-   Изменение параметра

Полный список действий в Office 365, для которых выполняется аудит, см. в статье [Поиск по журналу аудита в Центре безопасности и соответствия требованиям Office 365](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).

## <a name="turn-on-auditing-in-teams"></a>Включение аудита в Teams

Прежде чем приступить к просмотру данных аудита, необходимо сначала включить аудит в **центре безопасности &**(https://protection.office.com). Как это сделать, читайте в статье [Включение и отключение поиска в журнале аудита Office 365](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).


> [!IMPORTANT]
> Данные аудита доступны только с момента его включения.



## <a name="retrieve-teams-data-from-the-audit-log"></a>Извлечение данных Teams из журнала аудита

1.  Для извлечения журналов аудита войдите в [Центр безопасности и соответствия требованиям](https://go.microsoft.com/fwlink/?linkid=855775). В разделе **поиск & расследования**выберите пункт **Поиск в журнале аудита**.

2.  Используйте **Search** (Поиск) для фильтрации по действиям, датам и пользователям, по которым необходим аудит.

3.  Для дальнейшего анализа экспортируйте результаты в Excel.


> [!IMPORTANT]
> Данные аудита отображаются в журнале, только если аудит включен.

## <a name="video-techtip-using-audit-log-search-in-teams"></a>Видео: использование поиска по журналу аудита в Teams

Ансуман Ачарья (Ansuman Acharya), менеджер программ Teams, покажет вам, как выполнять поиск по журналу аудита для Teams в Центре безопасности и соответствия требованиям Office 365. 


> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]






