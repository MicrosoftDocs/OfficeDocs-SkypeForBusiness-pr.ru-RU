---
title: Поиск событий Microsoft Teams в журнале аудита
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Узнайте, как извлекать данные Microsoft Teams из журнала аудита Office 365.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 90645a7c2ffde142bdda80855b613877afc2f19e
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2019
ms.locfileid: "34432962"
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

Прежде чем приступить к просмотру данных аудита, необходимо сначала включить аудит в **центре соответствия требованиям безопасности _амп_**(https://protection.office.com). Как это сделать, читайте в статье [Включение и отключение поиска в журнале аудита Office 365](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).


> [!IMPORTANT]
> Данные аудита доступны только с момента его включения.



## <a name="retrieve-teams-data-from-the-audit-log"></a>Извлечение данных Teams из журнала аудита

1.  Для извлечения журналов аудита войдите в [Центр безопасности и соответствия требованиям](https://go.microsoft.com/fwlink/?linkid=855775). В разделе **Поиск _Амп_ расследования**выберите пункт **Поиск в журнале аудита**. ![Снимок экрана: страница поиска по журналу аудита](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  Используйте **Search** (Поиск) для фильтрации по действиям, датам и пользователям, по которым необходим аудит.

3.  Для дальнейшего анализа экспортируйте результаты в Excel.


> [!IMPORTANT]
> Данные аудита отображаются в журнале, только если аудит включен.

## <a name="video-techtip-using-audit-log-search-in-teams"></a>Видео: использование поиска по журналу аудита в Teams

Ансуман Ачарья (Ansuman Acharya), менеджер программ Teams, покажет вам, как выполнять поиск по журналу аудита для Teams в Центре безопасности и соответствия требованиям Office 365. 


> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]






