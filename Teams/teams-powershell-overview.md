---
title: Microsoft Teams Обзор PowerShell
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
# <a name="microsoft-teams-powershell-overview"></a>Microsoft Teams Обзор PowerShell

Microsoft Teams PowerShell — это набор командлетов для управления Teams непосредственно из командной строки PowerShell. В стандартном сценарии .NET Teams PowerShell работает в PowerShell 5.1 в Windows, PowerShell 6.x и более высоких уровнях на всех платформах, включая Azure Cloud Shell.

Прежде чем приступить к использованию PowerShell, необходимо установить [его.](teams-powershell-install.md) 

> [!WARNING]
> Известные проблемы с PowerShell 7 и Teams PowerShell. Мы рекомендуем использовать PowerShell 5.1, пока проблемы не будут устранены.

## <a name="releases"></a>Релизы


Teams PowerShell доступен в коллекции [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) двух типов выпусков.

- **Общие возможности доступности:** готовые к эксплуатации cmdlets, обновляются ежемесячно.

- **Общедоступный предварительный** просмотр: ранний доступ к функциям. Обновления могут обновляться чаще, чем обычно.

Подробные сведения о добавлении и усовершенствованиях функций для обоих выпусков можно получить в заметках Teams о выпуске [PowerShell.](teams-powershell-release-notes.md)


## <a name="manage-teams-with-powershell"></a>Управление Teams с помощью PowerShell

Модули PowerShell Teams для полного управления Teams:

- [Microsoft Teams PowerShell:](https://www.powershellgallery.com/packages/MicrosoftTeams/)модуль Teams PowerShell содержит командлеты для управления командами, чатом и каналами.

> [!NOTE]
> Общедоступный [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) версии 2.0 или более высокой версии включает все командлеты Skype для бизнеса Online Connector, предоставляющие один модуль для управления Teams PowerShell.

- [Skype для бизнеса PowerShell Connector](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell): соединитель Skype для бизнеса PowerShell теперь является частью модуля Teams PowerShell.

Полное руководство по управлению Teams с помощью этих модулей см. в Teams с помощью [Teams PowerShell.](teams-powershell-managing-teams.md)


## <a name="related-topics"></a>Статьи по теме

[Установка Teams PowerShell](teams-powershell-install.md)

[Управление Teams с помощью Teams PowerShell](teams-powershell-managing-teams.md)

[Teams Заметки о выпуске PowerShell](teams-powershell-release-notes.md)

[Microsoft Teams ссылки на cmdlet](/powershell/teams/?view=teams-ps)

[Skype для бизнеса ссылки на cmdlet](/powershell/skype/intro?view=skype-ps)

[Управление Microsoft Teams с ролями администратора](using-admin-roles.md)
