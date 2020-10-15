---
title: Переход из соединителя Skype для бизнеса Online в модуль PowerShell Teams
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: В этой статье рассказывается о том, как перейти с соединителя Skype для бизнеса Online на модуль команд PowerShell для управления группами.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e1838540e57cd91578e898818e2ed12e7b63a78
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469674"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Переход из соединителя Skype для бизнеса Online в модуль PowerShell Teams

Чтобы перейти от использования соединителя Skype для бизнеса Online с модулем Teams PowerShell для управления группами, вам потребуется обновить существующие сценарии PowerShell. В этой статье объясняется, как это сделать.

1. Установите последнюю версию модуля PowerShell для Teams. Инструкции можно найти в [статье Установка Microsoft Teams PowerShell](teams-powershell-install.md).
2. Удалите соединитель Skype для бизнеса Online. Для этого на панели управления перейдите в раздел **программы и компоненты**, выберите **Skype для бизнеса Online, модуль Windows PowerShell**и нажмите кнопку **Удалить**. 
3. В сценариях PowerShell измените имя модуля, на которое указывает ссылка ```Import-Module``` ```SkypeOnlineConnector``` ```LyncOnlineConnector``` ```MicrosoftTeams``` .

    Например, замените ```Import-Module -Name SkypeOnlineConnector``` на ```Import-Module -Name MicrosoftTeams``` .

> [!NOTE]
> Администраторы должны продолжать использовать [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) и импортировать сеанс перед использованием командлетов Skype для бизнеса Online. 

## <a name="related-topics"></a>Статьи по теме

[Установка Microsoft Teams PowerShell](teams-powershell-install.md)

[Управление группами с помощью PowerShell Teams](teams-powershell-managing-teams.md)

[Заметки о выпуске оболочки PowerShell для Teams](teams-powershell-release-notes.md)

[Справочник по командлетам Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Справочник по командлетам Skype для бизнеса](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
