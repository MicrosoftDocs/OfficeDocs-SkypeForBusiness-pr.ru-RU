---
title: Создание команд диспетчера людей в Microsoft Teams
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Узнайте, как с помощью сценария PowerShell создать команду для каждого руководителя с его руководителями в качестве участников группы.
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


При Microsoft Teams, а не запускать с чистого листа (без команд и каналов), настоятельно рекомендуем настроить базовую структуру команд и каналов. Это помогает предотвратить сппром команд, когда пользователи создают множество команд при создании каналов в существующих командах. Чтобы помочь вам при работе с хорошо спроектированной структурой команд и каналов, мы создали сценарий PowerShell, который создает команду для каждого из руководителей первой и второй строки с прямыми отчетами каждого руководителя в качестве участников группы. Этот сценарий не обновляет команды и каналы автоматически при добавлении или удалении людей из организации. Но это ценный инструмент, который можно использовать для наведения порядка в структуре Teams с самого начала. Этот сценарий читает azure AD, получает список руководителей и их прямые отчеты. Он использует этот список, чтобы создать одну команду на руководителя людей. 

## <a name="how-to-use-the-powershell-script"></a>Использование сценария PowerShell 

Начните с [](scripts/powershell-script-create-teams-from-managers-export-managers.md) запуска диспетчеров экспорта и их сценариев (предполагается, что вы уже запускали модули [Подключение-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) [и Подключение-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell). Диспетчеры экспорта и *их* сценарии создают файл с ExportedManagerDirects.txt со своими прямыми отчетами. 

Затем запустите сценарий Create new people manager teams (Создать [группу диспетчера людей).](scripts/powershell-script-create-teams-from-managers-new-teams.md) Этот сценарий читается в файле ExportedManagerDirects.txt и создает команду для каждого руководителя, а его непосредственные отчеты являются участниками. Если какой-либо руководитель или руководитель не Teams, сценарий пропускает их и не создает команду. (Просмотрите отчет, а затем повторно во время его включив Teams для всех, кому он нужен. Сценарий не создает вторую команду для руководителя, для него уже создана команда.)

Для каждой команды сценарий создает канал "Общие" и "Просто для развлечения". 

## <a name="best-practices"></a>Рекомендации

- Попросите каждого руководителя добавить веб-сайт для связи в связи скризис в качестве вкладки в общий канал для каждой команды. 

- Ознакомьтесь с новым приложением "Связь в случае скризис" в этой записи блога от 8 марта 2020 г. "Координация коммуникаций в случае скрикрибов с помощью [Microsoft Teams + Power Platform."](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)

## <a name="related-topics"></a>Статьи по теме

[Лучшие методики организации команд](best-practices-organizing.md)

[Создание команды для всей организации в Teams](create-an-org-wide-team.md)