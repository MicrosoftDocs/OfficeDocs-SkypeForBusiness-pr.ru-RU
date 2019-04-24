---
title: Поиск событий Microsoft Teams в журнале аудита
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Узнайте, как извлекать данные Microsoft Teams из журнала аудита Office 365.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 028d01a2ed05f3596cfe7cca299a1b8e35a15721
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32194994"
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="21a1c-103">Поиск событий Microsoft Teams в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="21a1c-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="21a1c-104">Журнал аудита помогает анализировать определенные действия в службах Office 365.</span><span class="sxs-lookup"><span data-stu-id="21a1c-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="21a1c-105">Примеры таких действий в Teams.</span><span class="sxs-lookup"><span data-stu-id="21a1c-105">For Teams, here are some of the activities that are audited:</span></span>

-   <span data-ttu-id="21a1c-106">Создание команды</span><span class="sxs-lookup"><span data-stu-id="21a1c-106">Team creation</span></span>

-   <span data-ttu-id="21a1c-107">Удаление команды</span><span class="sxs-lookup"><span data-stu-id="21a1c-107">Team deletion</span></span>

-   <span data-ttu-id="21a1c-108">Добавление канала</span><span class="sxs-lookup"><span data-stu-id="21a1c-108">Added channel</span></span>

-   <span data-ttu-id="21a1c-109">Изменение параметра</span><span class="sxs-lookup"><span data-stu-id="21a1c-109">Changed setting</span></span>

<span data-ttu-id="21a1c-110">Полный список действий в Office 365, для которых выполняется аудит, см. в статье [Поиск по журналу аудита в Центре безопасности и соответствия требованиям Office 365](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="21a1c-110">To see the complete list of activities that are audited in Office 365, read [Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="21a1c-111">Включение аудита в Teams</span><span class="sxs-lookup"><span data-stu-id="21a1c-111">Turn on auditing in Teams</span></span>

<span data-ttu-id="21a1c-112">Прежде чем можно посмотреть на данные аудита, необходимо выполнить первый параметр Включить аудит в **безопасности & центре соответствия требованиям**(https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="21a1c-112">Before you can look at audit data, you have to first turn on auditing in the **Security & Compliance Center**(https://protection.office.com).</span></span> <span data-ttu-id="21a1c-113">Как это сделать, читайте в статье [Включение и отключение поиска в журнале аудита Office 365](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="21a1c-113">For help turning on auditing, read [Turn Office 365 audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="21a1c-114">Данные аудита доступны только с момента его включения.</span><span class="sxs-lookup"><span data-stu-id="21a1c-114">Audit data is only available from the point at which you turned on Auditing.</span></span>



## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="21a1c-115">Извлечение данных Teams из журнала аудита</span><span class="sxs-lookup"><span data-stu-id="21a1c-115">Retrieve Teams data from the audit log</span></span>

1.  <span data-ttu-id="21a1c-116">Для извлечения журналов аудита войдите в [Центр безопасности и соответствия требованиям](https://go.microsoft.com/fwlink/?linkid=855775).</span><span class="sxs-lookup"><span data-stu-id="21a1c-116">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="21a1c-117">В разделе **Search & Investigation** (Поиск и анализ) выберите **Audit log search** (Поиск в журнале аудита).![Снимок экрана со страницей поиска по журналу аудита в Центре безопасности и соответствия требованиям.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="21a1c-117">Under **Search & Investigation**, select **Audit log search**.![Screenshot of the Audit log search page of the Security & Compliance Center.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)</span></span>

2.  <span data-ttu-id="21a1c-118">Используйте **Search** (Поиск) для фильтрации по действиям, датам и пользователям, по которым необходим аудит.</span><span class="sxs-lookup"><span data-stu-id="21a1c-118">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>

3.  <span data-ttu-id="21a1c-119">Для дальнейшего анализа экспортируйте результаты в Excel.</span><span class="sxs-lookup"><span data-stu-id="21a1c-119">Export your results to Excel for further analysis.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="21a1c-120">Данные аудита отображаются в журнале, только если аудит включен.</span><span class="sxs-lookup"><span data-stu-id="21a1c-120">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="21a1c-121">Видео: использование поиска по журналу аудита в Teams</span><span class="sxs-lookup"><span data-stu-id="21a1c-121">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="21a1c-122">Ансуман Ачарья (Ansuman Acharya), менеджер программ Teams, покажет вам, как выполнять поиск по журналу аудита для Teams в Центре безопасности и соответствия требованиям Office 365.</span><span class="sxs-lookup"><span data-stu-id="21a1c-122">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span> 


> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]






