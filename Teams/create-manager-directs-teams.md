---
title: Создание групп руководителей пользователей в Microsoft Teams
ms.reviewer: pbethi
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Сведения о том, как использовать сценарий PowerShell для создания группы для каждого руководителя с их прямыми участниками группы.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb6cd6ed74bebd0cbd729b828c152b9f04d1fc1f
ms.sourcegitcommit: cfaae3ecbf853766de788b4825a86e04f68868ca
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2020
ms.locfileid: "42796223"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a><span data-ttu-id="05f41-103">Создание групп руководителей пользователей в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="05f41-103">Create people manager teams in Microsoft Teams</span></span>


<span data-ttu-id="05f41-104">При развертывании Microsoft Teams, а не при запуске с помощью пустого содержания (без команд или каналов), настоятельно рекомендуется настроить базовую структуру команд и каналов.</span><span class="sxs-lookup"><span data-stu-id="05f41-104">When you roll out Microsoft Teams, rather than launching with a "blank slate" (no teams or channels), we strongly recommend that you set up a base framework of teams and channels.</span></span> <span data-ttu-id="05f41-105">Это помогает предотвратить "незначительное количество команд", где пользователи создают многочисленные команды, когда они должны создавать каналы в существующих группах.</span><span class="sxs-lookup"><span data-stu-id="05f41-105">This helps to prevent "team sprawl," where users create numerous teams when they should be creating channels in existing teams.</span></span> <span data-ttu-id="05f41-106">Чтобы приступить к работе с грамотно разработанной структурой и группами каналов, мы создали сценарий PowerShell, создающий группу для каждого из ваших двух и второй управляющих руководителей, каждый из которых является подчиненным сотрудникам в качестве участников команды.</span><span class="sxs-lookup"><span data-stu-id="05f41-106">To help you get started with a well-designed teams and channels structure, we've created a PowerShell script that creates a team for each of your first and second line people managers, with each manager's direct reports as team members.</span></span> <span data-ttu-id="05f41-107">Это сценарий "на момент времени" (он не обновляет команды и каналы автоматически при добавлении или удалении пользователей из организации).</span><span class="sxs-lookup"><span data-stu-id="05f41-107">This is a "point-in-time" script (it doesn't update your teams or channels automatically when people are added or removed from an organization).</span></span> <span data-ttu-id="05f41-108">Но это ценный инструмент, который можно использовать для создания определенного порядка в структуре Teams с начала.</span><span class="sxs-lookup"><span data-stu-id="05f41-108">But it's a valuable tool you can use to impose some order on your Teams structure from the start.</span></span> <span data-ttu-id="05f41-109">Этот сценарий читает Azure AD, получает список руководителей и их подчиненных отчетов.</span><span class="sxs-lookup"><span data-stu-id="05f41-109">This script reads your Azure AD, gets a list of managers and their direct reports.</span></span> <span data-ttu-id="05f41-110">Этот список используется для создания одной группы на одного руководителя пользователей.</span><span class="sxs-lookup"><span data-stu-id="05f41-110">It uses this list to create one team per people manager.</span></span> 

## <a name="how-to-use-the-powershell-script"></a><span data-ttu-id="05f41-111">Использование сценария PowerShell</span><span class="sxs-lookup"><span data-stu-id="05f41-111">How to use the PowerShell script</span></span> 

<span data-ttu-id="05f41-112">Начните с запуска [руководителей экспорта и их прямых сценариев](scripts/powershell-script-create-teams-from-managers-export-managers.md) (предполагается, что вы уже запустили модули PowerShell [Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) и [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) ).</span><span class="sxs-lookup"><span data-stu-id="05f41-112">Start by running the [Export managers and their directs script](scripts/powershell-script-create-teams-from-managers-export-managers.md) (which assumes you've already run the [Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) and [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell modules).</span></span> <span data-ttu-id="05f41-113">*Менеджеры экспорта и их прямые* сценарии создают файл с разделителями-знаками табуляции (ExportedManagerDirects. txt), который содержит список всех руководителей с подчиненными отчетами.</span><span class="sxs-lookup"><span data-stu-id="05f41-113">The *Export managers and their directs* script creates a tab-delimited file (ExportedManagerDirects.txt) that lists all managers with their direct reports.</span></span> 

<span data-ttu-id="05f41-114">Затем запустите сценарий " [Создание новых пользователей" в диспетчере групп](scripts/powershell-script-create-teams-from-managers-new-teams.md).</span><span class="sxs-lookup"><span data-stu-id="05f41-114">Then, run the [Create new people manager teams script](scripts/powershell-script-create-teams-from-managers-new-teams.md).</span></span> <span data-ttu-id="05f41-115">Этот сценарий считывает данные в файле ExportedManagerDirects. txt и создает группу для каждого руководителя, а прямые отчеты этого руководителя — в качестве участников.</span><span class="sxs-lookup"><span data-stu-id="05f41-115">This script reads in the ExportedManagerDirects.txt file and creates a team for each manager, with that manager's direct reports as members.</span></span> <span data-ttu-id="05f41-116">Если какой-либо руководитель не включен для Teams, сценарий пропускает их и не создает группу.</span><span class="sxs-lookup"><span data-stu-id="05f41-116">If any manager or direct isn't enabled for Teams, the script skips them and doesn't create a team.</span></span> <span data-ttu-id="05f41-117">(Просмотрите отчет, а затем повторно запустите сценарий после включения Teams для тех, кому это нужно.</span><span class="sxs-lookup"><span data-stu-id="05f41-117">(Review the report, then rerun the script after you've turned on Teams for anybody who needs it.</span></span> <span data-ttu-id="05f41-118">Сценарий не создаст вторую команду для всех руководителей, для которых она уже создана.</span><span class="sxs-lookup"><span data-stu-id="05f41-118">The script won't create a second team for any manager it's already created a team for.)</span></span>

<span data-ttu-id="05f41-119">Для каждой команды сценарий создает общие и "только для забавного" канала.</span><span class="sxs-lookup"><span data-stu-id="05f41-119">For each team, the script creates a General and "Just for fun" channel.</span></span> 

## <a name="best-practices"></a><span data-ttu-id="05f41-120">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="05f41-120">Best practices</span></span>

- <span data-ttu-id="05f41-121">Попросите каждого из руководителей сотрудников добавить веб-сайт некритической связи в качестве вкладки в канал общего канала для каждой команды.</span><span class="sxs-lookup"><span data-stu-id="05f41-121">Ask each people manager to add your organization's crisis communications website as a tab to the General channel for each team.</span></span> 

- <span data-ttu-id="05f41-122">Ознакомьтесь с новым приложением по аварийному взаимодействии, прочитав эту запись в блоге 8 марта 2020: [координирование некритических соединений с помощью Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span><span class="sxs-lookup"><span data-stu-id="05f41-122">Check out the new Crisis Communications app by reading this March 8, 2020 blog post: [Coordinate crisis communications using Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span></span>

## <a name="related-topics"></a><span data-ttu-id="05f41-123">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="05f41-123">Related topics</span></span>

[<span data-ttu-id="05f41-124">Рекомендации по упорядочению команд</span><span class="sxs-lookup"><span data-stu-id="05f41-124">Best practices for organizing teams</span></span>](best-practices-organizing.md)

[<span data-ttu-id="05f41-125">Создание команды для всей организации в Teams</span><span class="sxs-lookup"><span data-stu-id="05f41-125">Create an org-wide team in Teams</span></span>](create-an-org-wide-team.md)
