---
title: Общие сведения о Microsoft Teams PowerShell
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
description: Сведения об использовании элементов управления PowerShell для управления Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a5986a730ed678d45360d89efbd35693134c2a6a
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814368"
---
# <a name="microsoft-teams-powershell-overview"></a>Общие сведения о Microsoft Teams PowerShell

Microsoft Teams PowerShell — это набор командлетов, предназначенных для управления группами непосредственно из командной строки PowerShell. Написанный в стандарте .NET Teams PowerShell работает на PowerShell 5,1 для Windows, PowerShell 6. x и более новых версий на всех платформах, включая Azure Shell.

Прежде чем приступить к работе с оболочкой PowerShell, необходимо [установить ее](teams-powershell-install.md). 

> [!WARNING]
> Обнаружены проблемы с PowerShell 7 и Teams PowerShell. Мы рекомендуем использовать PowerShell 5,1, пока проблемы не будут устранены.

## <a name="releases"></a>Оболочек


В [коллекции оболочки PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) для Teams PowerShell доступны два типа выпусков.

- **Общая доступность (GA)**: командлеты для подготовки к производству, обновленные ежемесячно.

- **Общедоступный предварительный просмотр**: ранний доступ к функциям. Может обновляться чаще, чем в GA.

Подробная информация о дополнениях и улучшениях для обоих выпусков, читайте в статье сведения [о выпуске оболочки PowerShell для Teams](teams-powershell-release-notes.md).


## <a name="manage-teams-with-powershell"></a>Управление группами с помощью PowerShell

Для полного управления группами вы будете использовать модули Teams PowerShell.

- [Модуль Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/): модуль команд PowerShell Teams включает командлеты для управления группами, чат и каналами.

> [!NOTE]
> Новейшая [общедоступная версия оболочки PowerShell для Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/) поддерживается с помощью соединителя Skype для бизнеса Online, что обеспечивает единый модуль для управления оболочкой PowerShell.

- [Соединитель PowerShell для Skype для бизнеса](https://www.microsoft.com/download/details.aspx?id=39366): теперь соединитель PowerShell для Skype для бизнеса является частью модуля Teams PowerShell.

Полный Руководство по управлению группами с использованием этих модулей можно найти в разделе [Управление группами с помощью PowerShell Teams](teams-powershell-managing-teams.md).


## <a name="related-topics"></a>См. также

[Установка оболочки PowerShell для Teams](teams-powershell-install.md)

[Управление группами с помощью PowerShell Teams](teams-powershell-managing-teams.md)

[Заметки о выпуске оболочки PowerShell для Teams](teams-powershell-release-notes.md)

[Справочник по командлетам Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Справочник по командлетам Skype для бизнеса](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Управление Microsoft Teams с ролями администратора](using-admin-roles.md)
