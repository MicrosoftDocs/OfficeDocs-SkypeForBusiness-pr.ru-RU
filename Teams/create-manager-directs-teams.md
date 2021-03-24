---
title: Создание групп менеджеров людей в Microsoft Teams
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Узнайте, как с помощью сценария PowerShell создать команду для каждого руководителя со своими непосредственными участниками.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fa7c82ec584791107e5d269ee40bccba272d20b4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094415"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Создание команд диспетчера людей в Microsoft Teams


При выпуске Microsoft Teams вместо запуска с чистого листа (без команд и каналов) настоятельно рекомендуется создать базовую структуру команд и каналов. Это помогает предотвратить спрайт групп, когда пользователи создают множество команд при создании каналов в существующих командах. Чтобы помочь вам начать работу с хорошо спроектированной структурой команд и каналов, мы создали сценарий PowerShell, который создает группу для каждого из руководителей первого и второго строки с прямыми отчетами в качестве участников группы. Этот сценарий не обновляет команды и каналы автоматически при добавлении или удалении людей из организации. Но это ценный инструмент, с помощью который можно с самого начала обеспечить определенный порядок в структуре Teams. Этот сценарий читает ваш Azure AD, получает список руководителей и их прямые отчеты. Он использует этот список для создания команды на каждого руководителя. 

## <a name="how-to-use-the-powershell-script"></a>Использование сценария PowerShell 

Начните с [](scripts/powershell-script-create-teams-from-managers-export-managers.md) запуска диспетчеров экспорта и их сценариев (предполагается, что вы уже запускали модули [PowerShell Connect-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) и [Connect-MicrosoftTeams).](/powershell/module/teams/connect-microsoftteams?view=teams-ps) Диспетчеры экспорта и *их* сценарии создают файл со списком ExportedManagerDirects.txt с прямыми отчетами. 

Затем запустите сценарий [команд диспетчера новых людей.](scripts/powershell-script-create-teams-from-managers-new-teams.md) Этот сценарий читает файл ExportedManagerDirects.txt и создает команду для каждого руководителя с прямыми отчетами в качестве участников. Если какой-либо руководитель или руководитель не включен для Teams, сценарий пропускает их и не создает команду. (Просмотрите отчет, а затем повторно включив Teams для всех, кому он нужен. Сценарий не создает вторую команду для руководителя, для него уже создана команда.)

Для каждой команды сценарий создает канал "Общее" и "Только для развлечения". 

## <a name="best-practices"></a>Рекомендации

- Попросите каждого руководителя добавить веб-сайт организации в качестве вкладки для канала "Общее" для каждой команды. 

- Ознакомьтесь с новым приложением для связи в случае непредусмотрения, прочитав запись блога от 8 марта 2020 г. "Координация коммуникаций в случае непредусмотрения с помощью [Microsoft Teams + Power Platform".](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)

## <a name="related-topics"></a>Статьи по теме

[Лучшие методики организации команд](best-practices-organizing.md)

[Создание команды для всей организации в Teams](create-an-org-wide-team.md)