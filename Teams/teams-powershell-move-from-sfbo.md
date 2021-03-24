---
title: Переход из Соединителю Skype для бизнеса Online в модуль Teams PowerShell
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Узнайте, как перейти с Соединителю Skype для бизнеса Online на модуль Teams PowerShell для управления Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5a2b502edc84c853a0a140a11f8c028b7c78aca6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094130"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="893a9-103">Переход из Соединителю Skype для бизнеса Online в модуль Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="893a9-103">Move from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="893a9-104">Чтобы перейти от использования Соединителю Skype для бизнеса Online к модуле Teams PowerShell для управления Teams, необходимо обновить существующие сценарии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="893a9-104">To move from using Skype for Business Online Connector to the Teams PowerShell module to manage Teams, you'll need to update your existing PowerShell scripts.</span></span> <span data-ttu-id="893a9-105">В этой статье объясняется, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="893a9-105">This article explains how to do this.</span></span>

1. <span data-ttu-id="893a9-106">Установите последнюю версию модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="893a9-106">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="893a9-107">По шагам [см. установку Microsoft Teams Powershell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="893a9-107">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="893a9-108">Удалить соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="893a9-108">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="893a9-109">Для этого на панели управления перейдите в приложение "Программы и компонентов", выберите Skype для бизнеса **Online, Windows PowerShell** модуль, а затем выберите **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="893a9-109">To do this, in Control Panel, go **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span> 
3. <span data-ttu-id="893a9-110">В сценариях PowerShell измените имя модуля, на которое ссылается ```Import-Module``` ```SkypeOnlineConnector``` ```LyncOnlineConnector``` ```MicrosoftTeams``` ссылка.</span><span class="sxs-lookup"><span data-stu-id="893a9-110">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from ```SkypeOnlineConnector``` or ```LyncOnlineConnector``` to ```MicrosoftTeams```.</span></span>

    <span data-ttu-id="893a9-111">Например, измените ```Import-Module -Name SkypeOnlineConnector``` на ```Import-Module -Name MicrosoftTeams``` .</span><span class="sxs-lookup"><span data-stu-id="893a9-111">For example, change ```Import-Module -Name SkypeOnlineConnector``` to ```Import-Module -Name MicrosoftTeams```.</span></span>
4. <span data-ttu-id="893a9-112">При использовании модуля Teams PowerShell 2.0 или более поздней, измените new-csOnlineSession на Connect-MicrosoftTeams.</span><span class="sxs-lookup"><span data-stu-id="893a9-112">When using Teams PowerShell Module 2.0 or later, change New-csOnlineSession to Connect-MicrosoftTeams.</span></span> 

```powershell
  # When using Teams PowerShell Module 1.1.6
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfbSession
   
   # When using Teams PowerShell Module 2.0 or later
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="related-topics"></a><span data-ttu-id="893a9-113">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="893a9-113">Related topics</span></span>

[<span data-ttu-id="893a9-114">Установка Microsoft Teams Powershell</span><span class="sxs-lookup"><span data-stu-id="893a9-114">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="893a9-115">Управление Teams с помощью Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="893a9-115">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="893a9-116">Заметки о выпуске Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="893a9-116">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="893a9-117">Справочник по командлетам Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="893a9-117">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="893a9-118">Справочник по cmdlet в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="893a9-118">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)