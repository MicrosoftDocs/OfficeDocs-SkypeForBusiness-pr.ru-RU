---
title: Обзор Microsoft Teams PowerShell
ms.reviewer: ''
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Узнайте, как использовать элементы управления PowerShell для управления Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 12360110df90fb5de2e3e4547534c8569cc5537a
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852160"
---
# <a name="microsoft-teams-powershell-overview"></a>Обзор Microsoft Teams PowerShell

Microsoft Teams PowerShell — это набор командлетов для управления Teams непосредственно из командной строки PowerShell. Teams PowerShell, написанный в стандарте .NET, работает в PowerShell 5.1 для Windows, PowerShell 6.x и более высоких версиях на всех платформах, включая облачную оболочку Azure.

Прежде чем приступить к использованию PowerShell, необходимо [установить его.](teams-powershell-install.md) 

> [!WARNING]
> Известные проблемы с PowerShell 7 и Teams PowerShell. Мы рекомендуем использовать PowerShell 5.1, пока проблемы не будут устранены.

## <a name="releases"></a>Выпуски


Teams PowerShell доступен в коллекции [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) двух типов.

- **Общая доступность (GA)**: готовые к эксплуатации cmdlets, обновляются ежемесячно.

- **Общедоступный предварительный** просмотр: ранний доступ к функциям. Может обновляться чаще, чем обычно.

Подробные сведения о добавлении и улучшении функций обоих выпусков можно получить в заметках [о выпуске Teams PowerShell.](teams-powershell-release-notes.md)


## <a name="manage-teams-with-powershell"></a>Управление Teams с помощью PowerShell

Модули Teams PowerShell используются для полного управления Teams.

- [Модуль Microsoft Teams PowerShell:](https://www.powershellgallery.com/packages/MicrosoftTeams/)модуль Teams PowerShell содержит командлеты для управления командами, чатом и каналами.

> [!NOTE]
> Последний [общедоступный выпуск Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) интегрирован со Skype для бизнеса Online Connector, что обеспечивает единый модуль для управления Teams PowerShell.

- [Соединитель Skype для бизнеса PowerShell Connector](https://www.microsoft.com/download/details.aspx?id=39366): соединитель Skype для бизнеса PowerShell теперь является частью модуля Teams PowerShell.

Полное руководство по управлению Teams с помощью этих модулей см. в руководстве [Teams с помощью Teams PowerShell.](teams-powershell-managing-teams.md)


## <a name="related-topics"></a>Статьи по теме

[Установка Teams PowerShell](teams-powershell-install.md)

[Управление Teams с помощью Teams PowerShell](teams-powershell-managing-teams.md)

[Заметки о выпуске Teams PowerShell](teams-powershell-release-notes.md)

[Справочник по командлетам Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Справочник по cmdlet в Skype для бизнеса](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Управление Microsoft Teams с ролями администратора](using-admin-roles.md)
