---
title: Создание команд диспетчера людей в Microsoft Teams
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Узнайте, как с помощью сценария PowerShell создать команду для каждого руководителя с его руководителями в качестве участников группы.
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
# <a name="create-people-manager-teams-in-microsoft-teams"></a><span data-ttu-id="227c2-103">Создание команд диспетчера людей в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="227c2-103">Create people manager teams in Microsoft Teams</span></span>


<span data-ttu-id="227c2-104">При Microsoft Teams, а не запускать с чистого листа (без команд и каналов), настоятельно рекомендуем настроить базовую структуру команд и каналов.</span><span class="sxs-lookup"><span data-stu-id="227c2-104">When you roll out Microsoft Teams, rather than launching with a "blank slate" (no teams or channels), we strongly recommend that you set up a base framework of teams and channels.</span></span> <span data-ttu-id="227c2-105">Это помогает предотвратить сппром команд, когда пользователи создают множество команд при создании каналов в существующих командах.</span><span class="sxs-lookup"><span data-stu-id="227c2-105">This helps to prevent "team sprawl," where users create numerous teams when they should be creating channels in existing teams.</span></span> <span data-ttu-id="227c2-106">Чтобы помочь вам при работе с хорошо спроектированной структурой команд и каналов, мы создали сценарий PowerShell, который создает команду для каждого из руководителей первой и второй строки с прямыми отчетами каждого руководителя в качестве участников группы.</span><span class="sxs-lookup"><span data-stu-id="227c2-106">To help you get started with a well-designed teams and channels structure, we've created a PowerShell script that creates a team for each of your first and second line people managers, with each manager's direct reports as team members.</span></span> <span data-ttu-id="227c2-107">Этот сценарий не обновляет команды и каналы автоматически при добавлении или удалении людей из организации.</span><span class="sxs-lookup"><span data-stu-id="227c2-107">This is a "point-in-time" script (it doesn't update your teams or channels automatically when people are added or removed from an organization).</span></span> <span data-ttu-id="227c2-108">Но это ценный инструмент, который можно использовать для наведения порядка в структуре Teams с самого начала.</span><span class="sxs-lookup"><span data-stu-id="227c2-108">But it's a valuable tool you can use to impose some order on your Teams structure from the start.</span></span> <span data-ttu-id="227c2-109">Этот сценарий читает azure AD, получает список руководителей и их прямые отчеты.</span><span class="sxs-lookup"><span data-stu-id="227c2-109">This script reads your Azure AD, gets a list of managers and their direct reports.</span></span> <span data-ttu-id="227c2-110">Он использует этот список, чтобы создать одну команду на руководителя людей.</span><span class="sxs-lookup"><span data-stu-id="227c2-110">It uses this list to create one team per people manager.</span></span> 

## <a name="how-to-use-the-powershell-script"></a><span data-ttu-id="227c2-111">Использование сценария PowerShell</span><span class="sxs-lookup"><span data-stu-id="227c2-111">How to use the PowerShell script</span></span> 

<span data-ttu-id="227c2-112">Начните с [](scripts/powershell-script-create-teams-from-managers-export-managers.md) запуска диспетчеров экспорта и их сценариев (предполагается, что вы уже запускали модули [Подключение-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) [и Подключение-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell).</span><span class="sxs-lookup"><span data-stu-id="227c2-112">Start by running the [Export managers and their directs script](scripts/powershell-script-create-teams-from-managers-export-managers.md) (which assumes you've already run the [Connect-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) and [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell modules).</span></span> <span data-ttu-id="227c2-113">Диспетчеры экспорта и *их* сценарии создают файл с ExportedManagerDirects.txt со своими прямыми отчетами.</span><span class="sxs-lookup"><span data-stu-id="227c2-113">The *Export managers and their directs* script creates a tab-delimited file (ExportedManagerDirects.txt) that lists all managers with their direct reports.</span></span> 

<span data-ttu-id="227c2-114">Затем запустите сценарий Create new people manager teams (Создать [группу диспетчера людей).](scripts/powershell-script-create-teams-from-managers-new-teams.md)</span><span class="sxs-lookup"><span data-stu-id="227c2-114">Then, run the [Create new people manager teams script](scripts/powershell-script-create-teams-from-managers-new-teams.md).</span></span> <span data-ttu-id="227c2-115">Этот сценарий читается в файле ExportedManagerDirects.txt и создает команду для каждого руководителя, а его непосредственные отчеты являются участниками.</span><span class="sxs-lookup"><span data-stu-id="227c2-115">This script reads in the ExportedManagerDirects.txt file and creates a team for each manager, with that manager's direct reports as members.</span></span> <span data-ttu-id="227c2-116">Если какой-либо руководитель или руководитель не Teams, сценарий пропускает их и не создает команду.</span><span class="sxs-lookup"><span data-stu-id="227c2-116">If any manager or direct isn't enabled for Teams, the script skips them and doesn't create a team.</span></span> <span data-ttu-id="227c2-117">(Просмотрите отчет, а затем повторно во время его включив Teams для всех, кому он нужен.</span><span class="sxs-lookup"><span data-stu-id="227c2-117">(Review the report, then rerun the script after you've turned on Teams for anybody who needs it.</span></span> <span data-ttu-id="227c2-118">Сценарий не создает вторую команду для руководителя, для него уже создана команда.)</span><span class="sxs-lookup"><span data-stu-id="227c2-118">The script won't create a second team for any manager it's already created a team for.)</span></span>

<span data-ttu-id="227c2-119">Для каждой команды сценарий создает канал "Общие" и "Просто для развлечения".</span><span class="sxs-lookup"><span data-stu-id="227c2-119">For each team, the script creates a General and "Just for fun" channel.</span></span> 

## <a name="best-practices"></a><span data-ttu-id="227c2-120">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="227c2-120">Best practices</span></span>

- <span data-ttu-id="227c2-121">Попросите каждого руководителя добавить веб-сайт для связи в связи скризис в качестве вкладки в общий канал для каждой команды.</span><span class="sxs-lookup"><span data-stu-id="227c2-121">Ask each people manager to add your organization's crisis communications website as a tab to the General channel for each team.</span></span> 

- <span data-ttu-id="227c2-122">Ознакомьтесь с новым приложением "Связь в случае скризис" в этой записи блога от 8 марта 2020 г. "Координация коммуникаций в случае скрикрибов с помощью [Microsoft Teams + Power Platform."](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)</span><span class="sxs-lookup"><span data-stu-id="227c2-122">Check out the new Crisis Communications app by reading this March 8, 2020 blog post: [Coordinate crisis communications using Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span></span>

## <a name="related-topics"></a><span data-ttu-id="227c2-123">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="227c2-123">Related topics</span></span>

[<span data-ttu-id="227c2-124">Лучшие методики организации команд</span><span class="sxs-lookup"><span data-stu-id="227c2-124">Best practices for organizing teams</span></span>](best-practices-organizing.md)

[<span data-ttu-id="227c2-125">Создание команды для всей организации в Teams</span><span class="sxs-lookup"><span data-stu-id="227c2-125">Create an org-wide team in Teams</span></span>](create-an-org-wide-team.md)