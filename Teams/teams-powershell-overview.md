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
ms.openlocfilehash: 448658fb844052815e14b85e0c70a33cb737b72d
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768358"
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
> Общедоступный выпуск [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) версии 2.0 или более высокой версии включает все командлеты Skype для бизнеса Online Connector, обеспечивая единый модуль для управления Teams PowerShell.

- [Соединитель Skype для бизнеса PowerShell Connector](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell): соединитель Skype для бизнеса PowerShell теперь является частью модуля Teams PowerShell.

Полное руководство по управлению Teams с помощью этих модулей см. в руководстве [Teams с помощью Teams PowerShell.](teams-powershell-managing-teams.md)


## <a name="related-topics"></a>Статьи по теме

[Установка Teams PowerShell](teams-powershell-install.md)

[Управление Teams с помощью Teams PowerShell](teams-powershell-managing-teams.md)

[Заметки о выпуске Teams PowerShell](teams-powershell-release-notes.md)

[Справочник по командлетам Microsoft Teams](/powershell/teams/?view=teams-ps)

[Справочник по cmdlet в Skype для бизнеса](/powershell/skype/intro?view=skype-ps)

[Управление Microsoft Teams с ролями администратора](using-admin-roles.md)
