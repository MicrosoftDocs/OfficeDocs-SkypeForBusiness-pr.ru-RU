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
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Узнайте, как извлекать данные Microsoft Teams из журнала аудита Office 365.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ee0c5175e3712881b1f51b3c98156ba8f179012d
ms.sourcegitcommit: 0f6321d51b40f06855679c18f7313febfedd419a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793385"
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Поиск событий Microsoft Teams в журнале аудита
==================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Журнал аудита помогает анализировать определенные действия в службах Office 365. Примеры таких действий в Teams.

- Создание команды

- Удаление команды

- Добавление канала

- Изменение параметра

> [!NOTE]
> События аудита из закрытых каналов также регистрируются так же, как и для групп и стандартных каналов.

Полный список действий в Office 365, для которых выполняется аудит, см. в статье [Поиск по журналу аудита в Центре безопасности и соответствия требованиям Office 365](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).

## <a name="turn-on-auditing-in-teams"></a>Включение аудита в Teams

Прежде чем приступить к просмотру данных аудита, необходимо сначала включить аудит в [центре безопасности & соответствия требованиям](https://protection.office.com). Как это сделать, читайте в статье [Включение и отключение поиска в журнале аудита Office 365](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).

> [!IMPORTANT]
> Данные аудита доступны только с момента его включения.

## <a name="retrieve-teams-data-from-the-audit-log"></a>Извлечение данных Teams из журнала аудита


1.  Для извлечения журналов аудита войдите в [Центр безопасности и соответствия требованиям](https://go.microsoft.com/fwlink/?linkid=855775). В разделе **Поиск**выберите пункт **Поиск в журнале аудита**.



2. Используйте **Search** (Поиск) для фильтрации по действиям, датам и пользователям, по которым необходим аудит.

3. Для дальнейшего анализа экспортируйте результаты в Excel.

> [!IMPORTANT]
> Данные аудита отображаются в журнале, только если аудит включен.

## <a name="video-techtip-using-audit-log-search-in-teams"></a>Видео: использование поиска по журналу аудита в Teams

Ансуман Ачарья (Ansuman Acharya), менеджер программ Teams, покажет вам, как выполнять поиск по журналу аудита для Teams в Центре безопасности и соответствия требованиям Office 365. 

> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]
