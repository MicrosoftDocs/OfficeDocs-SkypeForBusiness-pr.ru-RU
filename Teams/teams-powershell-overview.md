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
ms.openlocfilehash: 5385430c7db8aab0adf1efbaec546134e9adf388
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "44943992"
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

Для полного управления группами вы будете использовать оба этих модуля PowerShell:

- [Модуль Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/): модуль команд PowerShell Teams включает командлеты для управления группами, чат и каналами.

- [Модуль PowerShell для Skype для бизнеса](https://www.microsoft.com/download/details.aspx?id=39366): модуль PowerShell для Skype для бизнеса, содержащий командлеты для управления собраниями, телефонной системой и политиками.

Полный Руководство по управлению группами с использованием этих модулей можно найти в разделе [Управление группами с помощью PowerShell Teams](teams-powershell-managing-teams.md).

> [!NOTE]
> Новейшая [общедоступная версия оболочки PowerShell для Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/) поддерживается с помощью соединителя Skype для бизнеса Online, что обеспечивает единый модуль для управления оболочкой PowerShell.

## <a name="related-topics"></a>Статьи по теме

[Установка оболочки PowerShell для Teams](teams-powershell-install.md)

[Управление группами с помощью PowerShell Teams](teams-powershell-managing-teams.md)

[Заметки о выпуске оболочки PowerShell для Teams](teams-powershell-release-notes.md)

[Справочник по командлетам Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Справочник по командлетам Skype для бизнеса](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Управление Microsoft Teams с ролями администратора](using-admin-roles.md)
