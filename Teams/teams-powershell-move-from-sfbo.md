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
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="820e6-103">Переход из соединителя Skype для бизнеса Online в модуль PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="820e6-103">Move from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="820e6-104">Чтобы перейти от использования соединителя Skype для бизнеса Online с модулем Teams PowerShell для управления группами, вам потребуется обновить существующие сценарии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="820e6-104">To move from using Skype for Business Online Connector to the Teams PowerShell module to manage Teams, you'll need to update your existing PowerShell scripts.</span></span> <span data-ttu-id="820e6-105">В этой статье объясняется, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="820e6-105">This article explains how to do this.</span></span>

1. <span data-ttu-id="820e6-106">Установите последнюю версию модуля PowerShell для Teams.</span><span class="sxs-lookup"><span data-stu-id="820e6-106">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="820e6-107">Инструкции можно найти в [статье Установка Microsoft Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="820e6-107">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="820e6-108">Удалите соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="820e6-108">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="820e6-109">Для этого на панели управления перейдите в раздел **программы и компоненты**, выберите **Skype для бизнеса Online, модуль Windows PowerShell**и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="820e6-109">To do this, in Control Panel, go **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span> 
3. <span data-ttu-id="820e6-110">В сценариях PowerShell измените имя модуля, на которое указывает ссылка ```Import-Module``` ```SkypeOnlineConnector``` ```LyncOnlineConnector``` ```MicrosoftTeams``` .</span><span class="sxs-lookup"><span data-stu-id="820e6-110">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from ```SkypeOnlineConnector``` or ```LyncOnlineConnector``` to ```MicrosoftTeams```.</span></span>

    <span data-ttu-id="820e6-111">Например, замените ```Import-Module -Name SkypeOnlineConnector``` на ```Import-Module -Name MicrosoftTeams``` .</span><span class="sxs-lookup"><span data-stu-id="820e6-111">For example, change ```Import-Module -Name SkypeOnlineConnector``` to ```Import-Module -Name MicrosoftTeams```.</span></span>

> [!NOTE]
> <span data-ttu-id="820e6-112">Администраторы должны продолжать использовать [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) и импортировать сеанс перед использованием командлетов Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="820e6-112">Admins should continue to use [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) and import the session before using Skype for Business Online cmdlets.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="820e6-113">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="820e6-113">Related topics</span></span>

[<span data-ttu-id="820e6-114">Установка Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="820e6-114">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="820e6-115">Управление группами с помощью PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="820e6-115">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="820e6-116">Заметки о выпуске оболочки PowerShell для Teams</span><span class="sxs-lookup"><span data-stu-id="820e6-116">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="820e6-117">Справочник по командлетам Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="820e6-117">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="820e6-118">Справочник по командлетам Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="820e6-118">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
