---
title: Создание групп менеджеров людей в Microsoft Teams
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Узнайте, как с помощью сценария PowerShell создать команду для каждого руководителя со своими непосредственными участниками.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fa7c82ec584791107e5d269ee40bccba272d20b4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094415"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a><span data-ttu-id="03288-103">Создание команд диспетчера людей в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="03288-103">Create people manager teams in Microsoft Teams</span></span>


<span data-ttu-id="03288-104">При выпуске Microsoft Teams вместо запуска с чистого листа (без команд и каналов) настоятельно рекомендуется создать базовую структуру команд и каналов.</span><span class="sxs-lookup"><span data-stu-id="03288-104">When you roll out Microsoft Teams, rather than launching with a "blank slate" (no teams or channels), we strongly recommend that you set up a base framework of teams and channels.</span></span> <span data-ttu-id="03288-105">Это помогает предотвратить спрайт групп, когда пользователи создают множество команд при создании каналов в существующих командах.</span><span class="sxs-lookup"><span data-stu-id="03288-105">This helps to prevent "team sprawl," where users create numerous teams when they should be creating channels in existing teams.</span></span> <span data-ttu-id="03288-106">Чтобы помочь вам начать работу с хорошо спроектированной структурой команд и каналов, мы создали сценарий PowerShell, который создает группу для каждого из руководителей первого и второго строки с прямыми отчетами в качестве участников группы.</span><span class="sxs-lookup"><span data-stu-id="03288-106">To help you get started with a well-designed teams and channels structure, we've created a PowerShell script that creates a team for each of your first and second line people managers, with each manager's direct reports as team members.</span></span> <span data-ttu-id="03288-107">Этот сценарий не обновляет команды и каналы автоматически при добавлении или удалении людей из организации.</span><span class="sxs-lookup"><span data-stu-id="03288-107">This is a "point-in-time" script (it doesn't update your teams or channels automatically when people are added or removed from an organization).</span></span> <span data-ttu-id="03288-108">Но это ценный инструмент, с помощью который можно с самого начала обеспечить определенный порядок в структуре Teams.</span><span class="sxs-lookup"><span data-stu-id="03288-108">But it's a valuable tool you can use to impose some order on your Teams structure from the start.</span></span> <span data-ttu-id="03288-109">Этот сценарий читает ваш Azure AD, получает список руководителей и их прямые отчеты.</span><span class="sxs-lookup"><span data-stu-id="03288-109">This script reads your Azure AD, gets a list of managers and their direct reports.</span></span> <span data-ttu-id="03288-110">Он использует этот список для создания команды на каждого руководителя.</span><span class="sxs-lookup"><span data-stu-id="03288-110">It uses this list to create one team per people manager.</span></span> 

## <a name="how-to-use-the-powershell-script"></a><span data-ttu-id="03288-111">Использование сценария PowerShell</span><span class="sxs-lookup"><span data-stu-id="03288-111">How to use the PowerShell script</span></span> 

<span data-ttu-id="03288-112">Начните с [](scripts/powershell-script-create-teams-from-managers-export-managers.md) запуска диспетчеров экспорта и их сценариев (предполагается, что вы уже запускали модули [PowerShell Connect-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) и [Connect-MicrosoftTeams).](/powershell/module/teams/connect-microsoftteams?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="03288-112">Start by running the [Export managers and their directs script](scripts/powershell-script-create-teams-from-managers-export-managers.md) (which assumes you've already run the [Connect-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) and [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell modules).</span></span> <span data-ttu-id="03288-113">Диспетчеры экспорта и *их* сценарии создают файл со списком ExportedManagerDirects.txt с прямыми отчетами.</span><span class="sxs-lookup"><span data-stu-id="03288-113">The *Export managers and their directs* script creates a tab-delimited file (ExportedManagerDirects.txt) that lists all managers with their direct reports.</span></span> 

<span data-ttu-id="03288-114">Затем запустите сценарий [команд диспетчера новых людей.](scripts/powershell-script-create-teams-from-managers-new-teams.md)</span><span class="sxs-lookup"><span data-stu-id="03288-114">Then, run the [Create new people manager teams script](scripts/powershell-script-create-teams-from-managers-new-teams.md).</span></span> <span data-ttu-id="03288-115">Этот сценарий читает файл ExportedManagerDirects.txt и создает команду для каждого руководителя с прямыми отчетами в качестве участников.</span><span class="sxs-lookup"><span data-stu-id="03288-115">This script reads in the ExportedManagerDirects.txt file and creates a team for each manager, with that manager's direct reports as members.</span></span> <span data-ttu-id="03288-116">Если какой-либо руководитель или руководитель не включен для Teams, сценарий пропускает их и не создает команду.</span><span class="sxs-lookup"><span data-stu-id="03288-116">If any manager or direct isn't enabled for Teams, the script skips them and doesn't create a team.</span></span> <span data-ttu-id="03288-117">(Просмотрите отчет, а затем повторно включив Teams для всех, кому он нужен.</span><span class="sxs-lookup"><span data-stu-id="03288-117">(Review the report, then rerun the script after you've turned on Teams for anybody who needs it.</span></span> <span data-ttu-id="03288-118">Сценарий не создает вторую команду для руководителя, для него уже создана команда.)</span><span class="sxs-lookup"><span data-stu-id="03288-118">The script won't create a second team for any manager it's already created a team for.)</span></span>

<span data-ttu-id="03288-119">Для каждой команды сценарий создает канал "Общее" и "Только для развлечения".</span><span class="sxs-lookup"><span data-stu-id="03288-119">For each team, the script creates a General and "Just for fun" channel.</span></span> 

## <a name="best-practices"></a><span data-ttu-id="03288-120">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="03288-120">Best practices</span></span>

- <span data-ttu-id="03288-121">Попросите каждого руководителя добавить веб-сайт организации в качестве вкладки для канала "Общее" для каждой команды.</span><span class="sxs-lookup"><span data-stu-id="03288-121">Ask each people manager to add your organization's crisis communications website as a tab to the General channel for each team.</span></span> 

- <span data-ttu-id="03288-122">Ознакомьтесь с новым приложением для связи в случае непредусмотрения, прочитав запись блога от 8 марта 2020 г. "Координация коммуникаций в случае непредусмотрения с помощью [Microsoft Teams + Power Platform".](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)</span><span class="sxs-lookup"><span data-stu-id="03288-122">Check out the new Crisis Communications app by reading this March 8, 2020 blog post: [Coordinate crisis communications using Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span></span>

## <a name="related-topics"></a><span data-ttu-id="03288-123">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="03288-123">Related topics</span></span>

[<span data-ttu-id="03288-124">Лучшие методики организации команд</span><span class="sxs-lookup"><span data-stu-id="03288-124">Best practices for organizing teams</span></span>](best-practices-organizing.md)

[<span data-ttu-id="03288-125">Создание команды для всей организации в Teams</span><span class="sxs-lookup"><span data-stu-id="03288-125">Create an org-wide team in Teams</span></span>](create-an-org-wide-team.md)