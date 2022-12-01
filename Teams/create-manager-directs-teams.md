---
title: Создание команд менеджеров по работе с людьми в Майкрософт Teams
ms.reviewer: pbethi
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Узнайте, как использовать скрипт PowerShell для создания команды для каждого руководителя с его прямыми клиентами в качестве участников команды.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 89a820a1b828621df2a129b7a972408e7280b3da
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198931"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Создание команд менеджеров по работе с людьми в Майкрософт Teams


При развертывании Майкрософт Teams вместо запуска с "пустым листом" (без команд или каналов) настоятельно рекомендуется настроить базовую платформу команд и каналов. Это помогает предотвратить "разрастание команд", когда пользователи создают многочисленные команды, когда они должны создавать каналы в существующих командах. Чтобы помочь вам приступить к работе с хорошо спроектированной структурой команд и каналов, мы создали сценарий PowerShell, который создает команду для каждого из ваших руководителей первого и второго звена с прямыми отчетами каждого руководителя в качестве участников команды. Это сценарий "на определенный момент времени" (он не обновляет команды или каналы автоматически при добавлении или удалении людей из организации). Но это ценный инструмент, который можно использовать для наложения порядка в структуре Teams с самого начала. Этот скрипт считывает Azure AD, получает список руководителей и их прямые отчеты. Этот список используется для создания одной команды для каждого менеджера по работе с людьми. 

## <a name="how-to-use-the-powershell-script"></a>Использование скрипта PowerShell 

Начните с запуска [диспетчеров экспорта и их прямого сценария](scripts/powershell-script-create-teams-from-managers-export-managers.md) (предполагается, что вы уже выполнили модули [PowerShell Connect-AzureAd](/powershell/module/azuread/connect-azuread) и [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams) ). Скрипт *экспорта диспетчеров и их прямых* операций создает файл с разделителями табуляции (ExportedManagerDirects.txt), в который перечислены все руководители с их прямыми отчетами. 

Затем запустите [сценарий Создание команд диспетчера людей](scripts/powershell-script-create-teams-from-managers-new-teams.md). Этот скрипт считывает файл ExportedManagerDirects.txt и создает команду для каждого руководителя с прямыми отчетами этого руководителя в качестве участников. Если какой-либо руководитель или прямой не включен для Teams, скрипт пропускает их и не создает команду. (Просмотрите отчет, а затем повторно запустите сценарий после включения Teams для всех, кто в нем нуждается. Скрипт не создаст вторую команду ни для одного менеджера, для него уже создана команда.

Для каждой команды скрипт создает канал "Общий" и "Просто для удовольствия". 

## <a name="best-practices"></a>Рекомендации

- Попросите каждого менеджера по работе с людьми добавить веб-сайт вашей организации в качестве вкладки в общий канал для каждой команды. 

- Ознакомьтесь с новым приложением Crisis Communications, прочитав эту запись блога от 8 марта 2020 г[. Координирование кризисных коммуникаций с помощью Майкрософт Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).

## <a name="related-topics"></a>См. также

[Рекомендации по организации команд](best-practices-organizing.md)

[Создание команды для всей организации в Teams](create-an-org-wide-team.md)