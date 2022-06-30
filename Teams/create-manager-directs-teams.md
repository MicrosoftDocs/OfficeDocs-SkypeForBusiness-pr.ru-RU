---
title: Создание команд менеджеров людей в Microsoft Teams
ms.reviewer: pbethi
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Узнайте, как использовать сценарий PowerShell для создания команды для каждого руководителя с его подчиненными в качестве участников команды.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd880e58b2c6818b8738afd5fb4e5efaf78642d4
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562588"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Создание команд менеджеров людей в Microsoft Teams


При развертывание Microsoft Teams вместо запуска с пустым листом (без команд или каналов) настоятельно рекомендуется настроить базовую платформу команд и каналов. Это помогает предотвратить "спранг групп", когда пользователи создают множество команд, когда им следует создавать каналы в существующих командах. Чтобы помочь вам приступить к работе с хорошо спроектированными командами и структурой каналов, мы создали сценарий PowerShell, который создает команду для каждого из руководителей первой и второй строки с прямыми отчетами каждого руководителя в качестве участников команды. Это скрипт "на определенный момент времени" (он не обновляет команды или каналы автоматически при добавлении или удалении пользователей из организации). Но это ценный инструмент, который можно использовать для наведении порядка в структуре Teams с начала. Этот сценарий считывает Azure AD, получает список руководителей и их прямые отчеты. Он использует этот список для создания одной команды для каждого руководителя. 

## <a name="how-to-use-the-powershell-script"></a>Использование скрипта PowerShell 

Начните с запуска диспетчеров экспорта и их скриптов [directs](scripts/powershell-script-create-teams-from-managers-export-managers.md) (предполагается, что вы уже выполнили модули [PowerShell Connect-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) и [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) ). Диспетчеры экспорта и их скрипт *directs* создают файл с разделителями табуляции (ExportedManagerDirects.txt), в котором перечислены все руководители с их прямыми отчетами. 

Затем запустите сценарий [create new people manager teams](scripts/powershell-script-create-teams-from-managers-new-teams.md). Этот сценарий считывает ExportedManagerDirects.txt файле и создает команду для каждого руководителя с непосредственными отчетами этого руководителя в качестве участников. Если какой-либо руководитель или прямой руководитель не включен для Teams, сценарий пропускает их и не создает команду. (Просмотрите отчет, а затем повторно запустите скрипт после включения Teams для всех, кому он нужен. Сценарий не создает вторую команду для любого руководителя, для него уже создана команда.)

Для каждой команды сценарий создает канал "Общие" и "Просто для интересного". 

## <a name="best-practices"></a>Рекомендации

- Попросите каждого руководителя сотрудников добавить веб-сайт для общения с клиентами в качестве вкладки в канал "Общие" для каждой команды. 

- Ознакомьтесь с новым приложением для коммуникаций в рамках антикризисного режима, прочитав эту запись блога от 8 марта 2020 г. "Координация коммуникаций с помощью [Microsoft Teams + Power Platform"](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).

## <a name="related-topics"></a>Статьи по теме

[Рекомендации по организации команд](best-practices-organizing.md)

[Создание команды для всей организации в Teams](create-an-org-wide-team.md)