---
title: "Поиск событий Microsoft Teams в журнале аудита | Служба поддержки Майкрософт"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Сведения об извлечении данных Microsoft Teams из журнала аудита."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 558db88d32229fcaef70ea5278d7437fbea92198
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2017
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="13fc9-103">Поиск событий Microsoft Teams в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="13fc9-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================

<span data-ttu-id="13fc9-104">Журнал аудита предоставляет особые возможности для поиска событий в службах Office 365.</span><span class="sxs-lookup"><span data-stu-id="13fc9-104">The Audit Log provides ad-hoc search capabilities into notable events across Office 365 services.</span></span> <span data-ttu-id="13fc9-105">Ниже представлено несколько примеров событий специально для Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="13fc9-105">For Microsoft Teams specifically, below are a few examples of events captured:</span></span>

-   <span data-ttu-id="13fc9-106">Создание команды</span><span class="sxs-lookup"><span data-stu-id="13fc9-106">Team Creation</span></span>

-   <span data-ttu-id="13fc9-107">Удаление команды</span><span class="sxs-lookup"><span data-stu-id="13fc9-107">Team Deletion</span></span>

-   <span data-ttu-id="13fc9-108">Добавление канала</span><span class="sxs-lookup"><span data-stu-id="13fc9-108">Added Channel</span></span>

-   <span data-ttu-id="13fc9-109">Изменение параметра</span><span class="sxs-lookup"><span data-stu-id="13fc9-109">Changed Setting</span></span>

<span data-ttu-id="13fc9-110">Полный список событий для Office 365 довольно велик и приведен [здесь](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities).</span><span class="sxs-lookup"><span data-stu-id="13fc9-110">The complete event list across Office 365 is quite extensive and can be found [here](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities).</span></span>

<span data-ttu-id="13fc9-111">Прежде чем просмотреть сведения аудита, нужно включить соответствующую функцию.</span><span class="sxs-lookup"><span data-stu-id="13fc9-111">Before you can dig into audit insights, auditing must first be enabled.</span></span> <span data-ttu-id="13fc9-112">Чтобы включить аудит, перейдите в Центр *безопасности и соответствия требованиям*.</span><span class="sxs-lookup"><span data-stu-id="13fc9-112">To enable Auditing, navigate to the *Security & Compliance* Admin Center.</span></span> <span data-ttu-id="13fc9-113">В области *Search for activity* (Поиск действия) выберите **Start recording now** (Начать запись).</span><span class="sxs-lookup"><span data-stu-id="13fc9-113">Under *Search for activity*, click on **Start recording now**.</span></span> <span data-ttu-id="13fc9-114">Через 24 часа данные аудита будут доступны в области *Audit Log Search* (Поиск в журнале аудита) на вкладке *Search & Investigation* (Поиск и анализ).</span><span class="sxs-lookup"><span data-stu-id="13fc9-114">After 24hrs, audit data will be available via *Audit Log Search* located under the *Search & Investigation* tab.</span></span>


| |  |
|---------|---------|
|![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image1.png)<br></br><span data-ttu-id="13fc9-115">Важно.</span><span class="sxs-lookup"><span data-stu-id="13fc9-115">Important:</span></span>     |<span data-ttu-id="13fc9-116">Эти данные начинаются с момента включения аудита.</span><span class="sxs-lookup"><span data-stu-id="13fc9-116">Audit data is only available from the point at which Auditing was enabled.</span></span>         |

![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image2.png)

<span data-ttu-id="13fc9-117">А теперь рассмотрим, как извлечь данные Microsoft Teams из журнала аудита:</span><span class="sxs-lookup"><span data-stu-id="13fc9-117">Now, let’s look at how to retrieve Microsoft Teams data from the Audit Log:</span></span>

1.  <span data-ttu-id="13fc9-118">Чтобы извлечь сведения из журнала аудита, перейдите в Центр [безопасности и соответствия требованиям](https://go.microsoft.com/fwlink/?linkid=855775).</span><span class="sxs-lookup"><span data-stu-id="13fc9-118">To retrieve Audit Log information, navigate to the [Security & Compliance Admin Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="13fc9-119">На вкладке *Search & Investigation* (Поиск и анализ) выберите **Audit log search** (Поиск в журнале аудита).</span><span class="sxs-lookup"><span data-stu-id="13fc9-119">Under *Search & Investigation*, select **Audit log search.**</span></span>

    <span data-ttu-id="13fc9-120">а.</span><span class="sxs-lookup"><span data-stu-id="13fc9-120">A</span></span>  <span data-ttu-id="13fc9-121">Microsoft Teams имеет определенные действия аудита, которые можно выбрать, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="13fc9-121">Microsoft Teams has defined audit activities that can be selected as shown below.</span></span>

![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  <span data-ttu-id="13fc9-122">Выбрав нужные действия, укажите диапазон дат и пользователей, для которых нужно получить сведения Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="13fc9-122">After selecting the activities of interest, supply a date range and users to retrieve Microsoft Teams information from.</span></span> <span data-ttu-id="13fc9-123">Нажмите кнопку **Найти** для получения результатов.</span><span class="sxs-lookup"><span data-stu-id="13fc9-123">Click **Search** to retrieve the results.</span></span>

3.  <span data-ttu-id="13fc9-124">Эти сведения можно экспортировать в Excel и при необходимости отфильтровать.</span><span class="sxs-lookup"><span data-stu-id="13fc9-124">This information can be exported to Excel and filtered as needed.</span></span>


|  | |
|---------|---------|
|![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image1.png)<br></br><span data-ttu-id="13fc9-125">Важно.</span><span class="sxs-lookup"><span data-stu-id="13fc9-125">Important:</span></span> |<span data-ttu-id="13fc9-126">Если функция аудита отключена, ее нужно включить, прежде чем в журнале аудита появятся данные.</span><span class="sxs-lookup"><span data-stu-id="13fc9-126">If auditing has not been enabled previously, that needs to be enabled before data will appear in the Audit Log.</span></span>         |
