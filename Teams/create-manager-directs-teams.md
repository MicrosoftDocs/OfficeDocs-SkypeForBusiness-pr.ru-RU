---
title: Создание групп руководителей пользователей в Microsoft Teams
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Сведения о том, как использовать сценарий PowerShell для создания группы для каждого руководителя с их прямыми участниками группы.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe57656eec61747dd0a43d475444e65d8600e222
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583678"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Создание групп руководителей пользователей в Microsoft Teams


При развертывании Microsoft Teams, а не при запуске с помощью пустого содержания (без команд или каналов), настоятельно рекомендуется настроить базовую структуру команд и каналов. Это помогает предотвратить "незначительное количество команд", где пользователи создают многочисленные команды, когда они должны создавать каналы в существующих группах. Чтобы приступить к работе с грамотно разработанной структурой и группами каналов, мы создали сценарий PowerShell, создающий группу для каждого из ваших двух и второй управляющих руководителей, каждый из которых является подчиненным сотрудникам в качестве участников команды. Это сценарий "на момент времени" (он не обновляет команды и каналы автоматически при добавлении или удалении пользователей из организации). Но это ценный инструмент, который можно использовать для создания определенного порядка в структуре Teams с начала. Этот сценарий читает Azure AD, получает список руководителей и их подчиненных отчетов. Этот список используется для создания одной группы на одного руководителя пользователей. 

## <a name="how-to-use-the-powershell-script"></a>Использование сценария PowerShell 

Начните с запуска [руководителей экспорта и их прямых сценариев](scripts/powershell-script-create-teams-from-managers-export-managers.md) (предполагается, что вы уже запустили модули PowerShell [Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) и [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) ). *Менеджеры экспорта и их прямые* сценарии создают файл с разделителями-знаками табуляции (ExportedManagerDirects.txt), который содержит список всех руководителей с подчиненными отчетами. 

Затем запустите сценарий " [Создание новых пользователей" в диспетчере групп](scripts/powershell-script-create-teams-from-managers-new-teams.md). Этот сценарий считывает данные из файла ExportedManagerDirects.txt и создает группу для каждого руководителя, а прямые отчеты этого руководителя — как участники. Если какой-либо руководитель не включен для Teams, сценарий пропускает их и не создает группу. (Просмотрите отчет, а затем повторно запустите сценарий после включения Teams для тех, кому это нужно. Сценарий не создаст вторую команду для всех руководителей, для которых она уже создана.

Для каждой команды сценарий создает общие и "только для забавного" канала. 

## <a name="best-practices"></a>Рекомендации

- Попросите каждого из руководителей сотрудников добавить веб-сайт некритической связи в качестве вкладки в канал общего канала для каждой команды. 

- Ознакомьтесь с новым приложением по аварийному взаимодействии, прочитав эту запись в блоге 8 марта 2020: [координирование некритических соединений с помощью Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).

## <a name="related-topics"></a>См. также

[Рекомендации по упорядочению команд](best-practices-organizing.md)

[Создание команды для всей организации в Teams](create-an-org-wide-team.md)
