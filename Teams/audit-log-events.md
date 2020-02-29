---
title: Поиск событий Microsoft Teams в журнале аудита
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.reviewer: anach
search.appverid: MET150
description: Узнайте, как извлекать данные Microsoft Teams из журнала аудита Office 365.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f53d1a0b5e600de9d38233b243dba3486b88bf1
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341627"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="ae42b-103">Поиск событий Microsoft Teams в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="ae42b-103">Search the audit log for events in Microsoft Teams</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="ae42b-104">Журнал аудита помогает анализировать определенные действия в службах Office 365.</span><span class="sxs-lookup"><span data-stu-id="ae42b-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="ae42b-105">Примеры таких действий в Teams.</span><span class="sxs-lookup"><span data-stu-id="ae42b-105">For Teams, here are some of the activities that are audited:</span></span>

- <span data-ttu-id="ae42b-106">Создание команды</span><span class="sxs-lookup"><span data-stu-id="ae42b-106">Team creation</span></span>

- <span data-ttu-id="ae42b-107">Удаление команды</span><span class="sxs-lookup"><span data-stu-id="ae42b-107">Team deletion</span></span>

- <span data-ttu-id="ae42b-108">Добавление канала</span><span class="sxs-lookup"><span data-stu-id="ae42b-108">Added channel</span></span>

- <span data-ttu-id="ae42b-109">Изменение параметра</span><span class="sxs-lookup"><span data-stu-id="ae42b-109">Changed setting</span></span>

> [!NOTE]
> <span data-ttu-id="ae42b-110">События аудита из закрытых каналов также регистрируются так же, как и для групп и стандартных каналов.</span><span class="sxs-lookup"><span data-stu-id="ae42b-110">Audit events from private channels are also logged as they are for teams and standard channels.</span></span>

<span data-ttu-id="ae42b-111">Полный список действий в Office 365, для которых выполняется аудит, см. в статье [Поиск по журналу аудита в Центре безопасности и соответствия требованиям Office 365](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="ae42b-111">To see the complete list of activities that are audited in Office 365, read [Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="ae42b-112">Включение аудита в Teams</span><span class="sxs-lookup"><span data-stu-id="ae42b-112">Turn on auditing in Teams</span></span>

<span data-ttu-id="ae42b-113">Прежде чем приступить к просмотру данных аудита, необходимо сначала включить аудит в [центре безопасности & соответствия требованиям](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="ae42b-113">Before you can look at audit data, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="ae42b-114">Как это сделать, читайте в статье [Включение и отключение поиска в журнале аудита Office 365](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="ae42b-114">For help turning on auditing, read [Turn Office 365 audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae42b-115">Данные аудита доступны только с момента его включения.</span><span class="sxs-lookup"><span data-stu-id="ae42b-115">Audit data is only available from the point at which you turned on Auditing.</span></span>

## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="ae42b-116">Извлечение данных Teams из журнала аудита</span><span class="sxs-lookup"><span data-stu-id="ae42b-116">Retrieve Teams data from the audit log</span></span>

1. <span data-ttu-id="ae42b-117">Для извлечения журналов аудита войдите в [Центр безопасности и соответствия требованиям](https://go.microsoft.com/fwlink/?linkid=855775).</span><span class="sxs-lookup"><span data-stu-id="ae42b-117">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="ae42b-118">В разделе **Поиск**выберите пункт **Поиск в журнале аудита**.</span><span class="sxs-lookup"><span data-stu-id="ae42b-118">Under **Search**, select **Audit log search**.</span></span>
1. <span data-ttu-id="ae42b-119">Используйте **Search** (Поиск) для фильтрации по действиям, датам и пользователям, по которым необходим аудит.</span><span class="sxs-lookup"><span data-stu-id="ae42b-119">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>
1. <span data-ttu-id="ae42b-120">Для дальнейшего анализа экспортируйте результаты в Excel.</span><span class="sxs-lookup"><span data-stu-id="ae42b-120">Export your results to Excel for further analysis.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae42b-121">Данные аудита отображаются в журнале, только если аудит включен.</span><span class="sxs-lookup"><span data-stu-id="ae42b-121">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="external-user-scenario"></a><span data-ttu-id="ae42b-122">Сценарий для внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="ae42b-122">External user scenario</span></span>

<span data-ttu-id="ae42b-123">Один сценарий, на основе которого вы можете следить, — это Добавление внешних пользователей в среду Teams с учетом перспективы бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ae42b-123">One scenario you might want to keep an eye on, from a business perspective, is the addition of external users to your Teams environment.</span></span> <span data-ttu-id="ae42b-124">Если включены внешние пользователи, рекомендуется наблюдать за их присутствием.</span><span class="sxs-lookup"><span data-stu-id="ae42b-124">If external users are enabled, then monitoring their presence is a good idea.</span></span>

![Снимок экрана: список событий, вызванных массовом удалением](media/TeamsExternalUserAddPolicy.png)

<span data-ttu-id="ae42b-126">Снимок экрана, на котором показано, как с помощью функции мониторинга внешних пользователей можно присвоить имя политике, задать уровень важности в соответствии с бизнес-потребностями, установить его как (в данном случае), а затем задать параметры, которые специально будут отслеживать только добавление. пользователей, которые не являются внутренними, и ограничьте это действие до Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ae42b-126">The screenshot of this policy to monitor external user adds allows you to name the policy, set the severity according to your business needs, set it as (in this case) a single activity, and then establish the parameters that will specifically monitor only the addition of non-internal users, and limit this activity to Microsoft Teams.</span></span>

<span data-ttu-id="ae42b-127">Результаты из этой политики будут доступны для просмотра в журнале событий:</span><span class="sxs-lookup"><span data-stu-id="ae42b-127">Then results from this policy will be able to be viewed in the activity log:</span></span>

![Снимок экрана: список событий, вызванных массовом удалением](media/TeamsExternalUserList.png)

<span data-ttu-id="ae42b-129">Здесь вы можете просмотреть соответствия в заданной вами политике и внести необходимые изменения, а также экспортировать результаты для использования в другом месте.</span><span class="sxs-lookup"><span data-stu-id="ae42b-129">Here you can review matches to the policy you've set, and make any adjustments as needed, or export the results to use elsewhere.</span></span>

## <a name="mass-delete-scenario"></a><span data-ttu-id="ae42b-130">Сценарий массового удаления</span><span class="sxs-lookup"><span data-stu-id="ae42b-130">Mass delete scenario</span></span>

<span data-ttu-id="ae42b-131">Как упоминалось выше, вы можете отслеживать сценарии удаления.</span><span class="sxs-lookup"><span data-stu-id="ae42b-131">As mentioned above, you can monitor deletion scenarios.</span></span> <span data-ttu-id="ae42b-132">Вы можете создать политику, которая будет отслеживать массовое удаление сайтов групп.</span><span class="sxs-lookup"><span data-stu-id="ae42b-132">It's possible to create a policy that would monitor mass deletion of Teams sites:</span></span>

![Снимок экрана: страница создания политики, на которой показана настройка политики для обнаружения удаления массовой команды](media/TeamsMassDeletePolicy.png)

<span data-ttu-id="ae42b-134">Как показано на снимке экрана, вы можете настроить различные параметры для этой политики, чтобы отслеживать удаления групп, в том числе серьезности, одно или повторяющиеся действия, а также параметры, ограничивающие это для групп и удаления сайта.</span><span class="sxs-lookup"><span data-stu-id="ae42b-134">As the screenshot shows, you can set many different parameters for this policy to monitor Teams deletions, including severity, single or repeated action, and parameters limiting this to Teams and site deletion.</span></span> <span data-ttu-id="ae42b-135">Это можно сделать независимо от шаблона или создать шаблон, который будет использоваться для создания политики, в зависимости от потребностей Организации.</span><span class="sxs-lookup"><span data-stu-id="ae42b-135">This can be done independently of a template, or you may have a template created to base this policy off, depending on your organizational needs.</span></span>

<span data-ttu-id="ae42b-136">После того как вы настроили политику, которая будет работать для вашего бизнеса, вы можете просмотреть результаты в журнале активности, как если бы они ни были запущены.</span><span class="sxs-lookup"><span data-stu-id="ae42b-136">Once you've established a policy that will work for your business, you can then review the results in the activity log as events are triggered:</span></span>

![Снимок экрана: список событий, вызванных массовом удалением](media/TeamsMassDeleteList.png)

<span data-ttu-id="ae42b-138">Вы можете применить фильтр к нужной политике для просмотра результатов этой политики.</span><span class="sxs-lookup"><span data-stu-id="ae42b-138">You can filter down to the policy you've set to see the results of that policy.</span></span> <span data-ttu-id="ae42b-139">Если результаты, которые вы получаете в журнале активности, неудовлетворительны (возможно, вы видите большое количество результатов или ничего не знаете), это поможет вам выполнить точную настройку запроса, чтобы сделать его более подходящим.</span><span class="sxs-lookup"><span data-stu-id="ae42b-139">If the results you're getting in the activity log are not satisfactory (maybe you're seeing a lot of results, or nothing at all), this may help you to fine-tune the query to make it more relevant to what you need it to do.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="ae42b-140">Видео: использование поиска по журналу аудита в Teams</span><span class="sxs-lookup"><span data-stu-id="ae42b-140">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="ae42b-141">Ансуман Ачарья (Ansuman Acharya), менеджер программ Teams, покажет вам, как выполнять поиск по журналу аудита для Teams в Центре безопасности и соответствия требованиям Office 365.</span><span class="sxs-lookup"><span data-stu-id="ae42b-141">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span>

> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]
