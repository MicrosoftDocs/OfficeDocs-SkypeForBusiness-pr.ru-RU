---
title: Azure Sentinel и Microsoft Teams
author: MicrosoftHeidi
ms.author: tracyp
manager: dansimp
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Советы по безопасности и учебные материалы для ИТ-администраторов по использованию Sentinel для отслеживания и обнаружения угроз, которые могут возникать в Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3b2c37f7f3731b34abb5337bf954250e0c3564d
ms.sourcegitcommit: 046b020cee8af00a1d0e5f5866f847d42e8ad9a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51712771"
---
# <a name="azure-sentinel-and-microsoft-teams"></a><span data-ttu-id="4e9bb-103">Azure Sentinel и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4e9bb-103">Azure Sentinel and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e9bb-104">Теперь у Azure Sentinel есть интегрированный соединитель.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-104">Azure Sentinel now has an integrated connector.</span></span> <span data-ttu-id="4e9bb-105">Дополнительные сведения см. в статье [Подключение журналов Office 365 к Azure Sentinel](/azure/sentinel/connect-office-365).</span><span class="sxs-lookup"><span data-stu-id="4e9bb-105">For more information, see [Connect Office 365 Logs to Azure Sentinel](/azure/sentinel/connect-office-365).</span></span> <span data-ttu-id="4e9bb-106">Таков рекомендуемый метод для сбора этих журналов; он заменяет собой методы сбора, описанные ниже.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-106">This is the recommended route for collecting these logs and supersedes the collection methods described below.</span></span>

<span data-ttu-id="4e9bb-107">Teams играет центральную роль во взаимодействии и распространении данных в облаке Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-107">Teams serves a central role in communication and data-sharing in the Microsoft 365 Cloud.</span></span> <span data-ttu-id="4e9bb-108">Так как служба Teams связана со многими базовыми технологиями в облаке, она может использовать преимущества человеческого и автоматизированного анализа.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-108">Since Teams touches on so many technologies in the Cloud, it can benefit from human and automated analysis.</span></span> <span data-ttu-id="4e9bb-109">Это относится как к *поиску в журналах*, так и *при отслеживании собраний в режиме реального времени*.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-109">This applies to both *hunting in logs*, and *real-time monitoring of meetings*.</span></span> <span data-ttu-id="4e9bb-110">Azure Sentinel предлагает эти решения администраторам.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-110">Azure Sentinel offers admins these solutions.</span></span>

> [!NOTE]
> <span data-ttu-id="4e9bb-111">Требуется освежить знания по Azure Sentinel?</span><span class="sxs-lookup"><span data-stu-id="4e9bb-111">Need a refresher on Azure Sentinel?</span></span> <span data-ttu-id="4e9bb-112">[Эта статья](/azure/sentinel/overview) как раз для этого.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-112">[This article](/azure/sentinel/overview) is just the thing.</span></span>

## <a name="sentinel-and-microsoft-teams-activity-logs"></a><span data-ttu-id="4e9bb-113">Sentinel и журналы действий Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4e9bb-113">Sentinel and Microsoft Teams Activity Logs</span></span>

<span data-ttu-id="4e9bb-114">В этой статье рассматривается сбор журналов действий Teams в Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-114">This article focuses on collecting Teams activity logs in Azure Sentinel.</span></span>

<span data-ttu-id="4e9bb-115">Sentinel позволяет администраторам управлять безопасностью в одном месте.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-115">Sentinel lets administrators do security management in one location.</span></span> <span data-ttu-id="4e9bb-116">Это включает в себя управление:</span><span class="sxs-lookup"><span data-stu-id="4e9bb-116">This includes managing:</span></span>

- <span data-ttu-id="4e9bb-117">Сторонними устройствами</span><span class="sxs-lookup"><span data-stu-id="4e9bb-117">Third-party devices</span></span>
- <span data-ttu-id="4e9bb-118">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="4e9bb-118">Microsoft Threat Protection</span></span>
- <span data-ttu-id="4e9bb-119">Рабочими нагрузками Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4e9bb-119">Microsoft 365 Workloads</span></span>

<span data-ttu-id="4e9bb-120">Книги Sentinel и модули Runbook могут сделать мониторинг безопасности *системным*.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-120">Sentinel workbooks and runbooks can make security monitoring *systematic*.</span></span> <span data-ttu-id="4e9bb-121">Хорошим первым шагом в этом процессе является сбор необходимых журналов для анализа.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-121">A good first step in this process is collecting the logs needed analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="4e9bb-122">В одном экземпляре Azure Sentinel можно использовать несколько подписок на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-122">More than one Microsoft 365 subscription can be surfaced in the same instance of Azure Sentinel.</span></span> <span data-ttu-id="4e9bb-123">Это позволит выполнять [отслеживание в режиме реального времени](/azure/sentinel/livestream) и обнаруживать угрозы в архивных файлах журнала.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-123">This will allow for [realtime monitoring](/azure/sentinel/livestream) and hunting for threats in historical log files.</span></span> <span data-ttu-id="4e9bb-124">Администраторы смогут выполнять поиск, используя [запросы в разных ресурсах](/azure/azure-monitor/log-query/cross-workspace-query), в одной группе ресурсов, в разных группах ресурсов или в другой подписке.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-124">Administrators will be able to hunt using [cross-resource queries](/azure/azure-monitor/log-query/cross-workspace-query), that is within a single resource group, across resource groups, or in another subscription.</span></span>

## <a name="step-1-collect-teams-logs-enable-audit-logs-in-microsoft-365"></a><span data-ttu-id="4e9bb-125">Шаг 1. Сбор журналов Teams: включение журналов аудита в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4e9bb-125">Step 1: Collect Teams logs: Enable Audit logs in Microsoft 365</span></span>

<span data-ttu-id="4e9bb-126">Так как Teams регистрирует действия через Microsoft 365, журналы аудита не собираются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-126">Because Teams logs activity through Microsoft 365, audit logs aren't collected by default.</span></span> <span data-ttu-id="4e9bb-127">Эту функцию можно включить, выполнив [следующие шаги](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="4e9bb-127">Turn on this feature with [these steps](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span> <span data-ttu-id="4e9bb-128">Данные Teams собираются для аудита Microsoft 365 в разделе *Audit.General*.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-128">Teams data is collected in the Microsoft 365 audit under *Audit.General*.</span></span>

## <a name="step-2-connect-office-365-logs-to-azure-sentinel"></a><span data-ttu-id="4e9bb-129">Шаг 2. Подключение журналов Office 365 к Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="4e9bb-129">Step 2: Connect Office 365 logs to Azure Sentinel</span></span>

<span data-ttu-id="4e9bb-130">Azure Sentinel предоставляет встроенный соединитель для журналов Office 365, который позволяет принимать данные Teams в Azure Sentinel вместе с другими данными Office 365.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-130">Azure Sentinel provides a built-in connector for Office 365 logs, which enables you to ingest Teams data into Azure Sentinel together with other Office 365 data.</span></span>
 
<span data-ttu-id="4e9bb-131">В Azure Sentinel включите соединитель данных Office 365.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-131">In Azure Sentinel, enable the Office 365 data connector.</span></span> <span data-ttu-id="4e9bb-132">Для получения дополнительной информации см. раздел [Документация Azure Sentinel](/azure/sentinel/connect-office-365).</span><span class="sxs-lookup"><span data-stu-id="4e9bb-132">For more information, see the [Azure Sentinel documentation](/azure/sentinel/connect-office-365).</span></span>

## <a name="helpful-hunting-kql-queries"></a><span data-ttu-id="4e9bb-133">Полезные запросы KQL для поиска</span><span class="sxs-lookup"><span data-stu-id="4e9bb-133">Helpful hunting KQL queries</span></span>

<span data-ttu-id="4e9bb-134">Используйте эти запросы, чтобы познакомиться с данными и средой Teams.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-134">Use these queries to familiarize yourself with your Teams data and Teams environment.</span></span> <span data-ttu-id="4e9bb-135">Понимание среды и ее поведения — это отличный первый шаг по выявлению подозрительных действий.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-135">Knowing how the environment should look and behave is a good first step in recognizing suspicious activity.</span></span> <span data-ttu-id="4e9bb-136">После этого вы можете перейти к поиску угроз.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-136">From there, you can branch out into threat hunting.</span></span>

### <a name="federated-external-users-query"></a><span data-ttu-id="4e9bb-137">Запросы федеративных внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="4e9bb-137">Federated external users query</span></span>

<span data-ttu-id="4e9bb-138">Получите список сайтов Teams с федеративными внешними пользователями.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-138">Get the list of Teams sites that have federated external users.</span></span> <span data-ttu-id="4e9bb-139">У этих пользователей есть доменное имя и/или суффикс UPN, которые не принадлежат вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-139">These users have a domain name and/or a UPN suffix that isn't owned by your organization.</span></span>

<span data-ttu-id="4e9bb-140">В этом примере запроса организации принадлежит домен contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-140">In this example query, the organization owns contoso.com.</span></span>

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where parse_json(Members)[0].Role == 3
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
```

> [!TIP]
> <span data-ttu-id="4e9bb-141">Дополнительные сведения о внешнем и гостевом типах доступа в Teams см. в разделе [Общение с пользователями из других организаций](communicate-with-users-from-other-organizations.md) или в разделе [Типы участников](teams-security-guide.md#participant-types) в руководстве по безопасности Teams.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-141">To learn more about External and Guest access types in Teams see [Communicate with users from other organizations](communicate-with-users-from-other-organizations.md), or the [Participant Types](teams-security-guide.md#participant-types) section in the Teams Security Guide.</span></span>

### <a name="who-recently-joined--whose-role-changed"></a><span data-ttu-id="4e9bb-142">Кто недавно присоединился или чья роль изменена</span><span class="sxs-lookup"><span data-stu-id="4e9bb-142">Who recently joined / Whose role changed</span></span>

<span data-ttu-id="4e9bb-143">Запросите определенного пользователя, чтобы проверить, был ли он добавлен в канал Teams за последние 7 дней или в течение недели:</span><span class="sxs-lookup"><span data-stu-id="4e9bb-143">Query a specific user to check if they were added to a Teams channel in the last seven days, or within a week:</span></span>

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members has "<DisplayName>" or Members has "<UserPrincipalName>"
| project TeamName, Operation, UserId, Members
```

<span data-ttu-id="4e9bb-144">Сделайте запрос о том, изменилась ли роль пользователя в команде за последние 7 дней:</span><span class="sxs-lookup"><span data-stu-id="4e9bb-144">Query whether a user's role changed for a Team in the last seven days:</span></span>

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '1'
``` 

### <a name="external-users-from-unknown-or-new-organizations"></a><span data-ttu-id="4e9bb-145">Внешние пользователи из неизвестных или новых организаций</span><span class="sxs-lookup"><span data-stu-id="4e9bb-145">External users from unknown or new organizations</span></span>

<span data-ttu-id="4e9bb-146">В Teams вы можете добавлять внешних пользователей в среду или каналы.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-146">In Teams, you can add external users to your environment or channels.</span></span> <span data-ttu-id="4e9bb-147">Организации часто имеют ограниченное количество ключевых партнеров и добавляют пользователей этих партнеров.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-147">Organizations often have a limited number of key partnerships and add users from among these partners.</span></span> <span data-ttu-id="4e9bb-148">Эта функция KQL ищет добавленных в команды внешних пользователей из организаций, которые раньше отсутствовали или не добавлялись.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-148">This KQL looks at external users added to teams who come from organizations that haven't been seen or added before.</span></span>

<span data-ttu-id="4e9bb-149">Дополнительные сведения см. в запросе в [GitHub сообщества Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml).</span><span class="sxs-lookup"><span data-stu-id="4e9bb-149">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml).</span></span>

### <a name="external-users-who-were-added-and-then-removed"></a><span data-ttu-id="4e9bb-150">Внешние пользователи, которые были добавлены, а затем удалены</span><span class="sxs-lookup"><span data-stu-id="4e9bb-150">External users who were added and then removed</span></span>

<span data-ttu-id="4e9bb-151">Злоумышленники с определенным уровнем доступа могут добавить новую внешнюю учетную запись в Teams, чтобы получить доступ и извлечь данные.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-151">Attackers with some level of existing access may add a new external account to Teams to access and exfiltrate data.</span></span> <span data-ttu-id="4e9bb-152">Они также могут быстро удалить этого пользователя, чтобы скрыть получение доступа.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-152">They may also quickly remove that user to hide that they made access.</span></span> <span data-ttu-id="4e9bb-153">Этот запрос используется для поиска внешних учетных записей, которые добавлены в Teams и быстро удалены, чтобы выявить подозрительное поведение.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-153">This query hunts for external accounts that are added to Teams and swiftly removed to help identify suspicious behavior.</span></span>

<span data-ttu-id="4e9bb-154">Дополнительные сведения см. в запросе в [GitHub сообщества Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml).</span><span class="sxs-lookup"><span data-stu-id="4e9bb-154">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml).</span></span>

### <a name="new-bot-or-application-added"></a><span data-ttu-id="4e9bb-155">Добавлен новый бот или приложение</span><span class="sxs-lookup"><span data-stu-id="4e9bb-155">New bot or application added</span></span>

<span data-ttu-id="4e9bb-156">Teams может включать приложения или ботов в команду для расширения набора функций (включая пользовательские приложения и боты).</span><span class="sxs-lookup"><span data-stu-id="4e9bb-156">Teams can include apps or bots in a Team to extend the feature set (including custom apps and bots).</span></span> <span data-ttu-id="4e9bb-157">В некоторых случаях приложение или бот могут использоваться для *сохраняемости* в Teams без необходимости учетной записи пользователя, а также могут получать доступ к файлам и другим данным.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-157">In some cases, an app or bot can be used for *persistence* in Teams without needing a user account, and can access files and other data.</span></span> <span data-ttu-id="4e9bb-158">Этот запрос используется для поиска новых приложений и ботов в Teams.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-158">This query hunts for apps or bots that are new to Teams.</span></span>

<span data-ttu-id="4e9bb-159">Дополнительные сведения см. в запросе в [GitHub сообщества Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml).</span><span class="sxs-lookup"><span data-stu-id="4e9bb-159">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml).</span></span>

### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a><span data-ttu-id="4e9bb-160">Учетные записи пользователей, являющихся владельцами большого количества команд</span><span class="sxs-lookup"><span data-stu-id="4e9bb-160">User accounts who are Owners of large numbers of Teams</span></span>

<span data-ttu-id="4e9bb-161">Злоумышленники, пытающиеся получить дополнительные права, могут назначать себе права владельцев большого количества разнообразных команд.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-161">Attackers looking to elevate their privileges may assign themselves Owner privileges of a large number of diverse teams.</span></span> <span data-ttu-id="4e9bb-162">*Обычно* пользователи создают и владеют несколькими командами, посвященным определенным темам.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-162">*Usually*, users create and own a few teams around specific topics.</span></span> <span data-ttu-id="4e9bb-163">Этот запрос KQL ищет подозрительные действия.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-163">This KQL query looks for suspicious behavior.</span></span>

<span data-ttu-id="4e9bb-164">Дополнительные сведения см. в запросе в [GitHub сообщества Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml).</span><span class="sxs-lookup"><span data-stu-id="4e9bb-164">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml).</span></span>

### <a name="many-team-deletions-by-a-single-user"></a><span data-ttu-id="4e9bb-165">Удаление большого количества команд одним пользователем</span><span class="sxs-lookup"><span data-stu-id="4e9bb-165">Many Team deletions by a single user</span></span>

<span data-ttu-id="4e9bb-166">Злоумышленники могут вызывать нарушения в работе и создавать угрозы проектам и данным, удаляя несколько команд.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-166">Attackers can cause disruptions and jeopardize projects and data by deleting multiple teams.</span></span> <span data-ttu-id="4e9bb-167">Так как команды обычно удаляются отдельными владельцами, централизованное удаление нескольких команд может быть признаком проблемы.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-167">Since teams are usually deleted by individual Owners, central deletion of many teams can be a sign of trouble.</span></span> <span data-ttu-id="4e9bb-168">Этот запрос KQL ищет отдельных пользователей, удаляющих несколько команд.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-168">This KQL looks for single users who delete multiple teams.</span></span>

<span data-ttu-id="4e9bb-169">Дополнительные сведения см. в запросе в [GitHub сообщества Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml).</span><span class="sxs-lookup"><span data-stu-id="4e9bb-169">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml).</span></span>

### <a name="expanding-your-threat-hunting-opportunities"></a><span data-ttu-id="4e9bb-170">Расширение возможностей охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="4e9bb-170">Expanding your threat hunting opportunities</span></span>

<span data-ttu-id="4e9bb-171">Объединение запросов из таких ресурсов, как Azure Active Directory (Azure AD) или других рабочих нагрузок Office 365, можно использовать с запросами Teams.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-171">Combining queries from resources like Azure Active Directory (Azure AD), or other Office 365 workloads can be used with Teams queries.</span></span> <span data-ttu-id="4e9bb-172">Например, объедините обнаружение подозрительных шаблонов в Azure AD SigninLogs и используйте эти выходные данные при поиске владельцев групп.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-172">For example, combine the detection of suspicious patterns in Azure AD SigninLogs, and use that output while hunting for Team Owners.</span></span>

```Kusto
let timeRange = 1d;
let lookBack = 7d;
let threshold_Failed = 5;
let threshold_FailedwithSingleIP = 20;
let threshold_IPAddressCount = 2;
let isGUID = "[0-9a-z]{8}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{12}";
let azPortalSignins = SigninLogs
| where TimeGenerated >= ago(timeRange)
// Azure Portal only and exclude non-failure Result Types
| where AppDisplayName has "Azure Portal" and ResultType !in ("0", "50125", "50140")
// Tagging identities not resolved to friendly names
| extend Unresolved = iff(Identity matches regex isGUID, true, false);
// Lookup up resolved identities from last 7 days
let identityLookup = SigninLogs
| where TimeGenerated >= ago(lookBack)
| where not(Identity matches regex isGUID)
| summarize by UserId, lu_UserDisplayName = UserDisplayName, lu_UserPrincipalName = UserPrincipalName;
// Join resolved names to unresolved list from portal signins
let unresolvedNames = azPortalSignins | where Unresolved == true | join kind= inner (
   identityLookup ) on UserId
| extend UserDisplayName = lu_UserDisplayName, UserPrincipalName = lu_UserPrincipalName
| project-away lu_UserDisplayName, lu_UserPrincipalName;
// Join Signins that had resolved names with list of unresolved that now have a resolved name
let u_azPortalSignins = azPortalSignins | where Unresolved == false | union unresolvedNames;
let failed_signins = (u_azPortalSignins
| extend Status = strcat(ResultType, ": ", ResultDescription), OS = tostring(DeviceDetail.operatingSystem), Browser = tostring(DeviceDetail.browser)
| extend FullLocation = strcat(Location,'|', LocationDetails.state, '|', LocationDetails.city)
| summarize TimeGenerated = makelist(TimeGenerated), Status = makelist(Status), IPAddresses = makelist(IPAddress), IPAddressCount = dcount(IPAddress), FailedLogonCount = count()
by UserPrincipalName, UserId, UserDisplayName, AppDisplayName, Browser, OS, FullLocation
| mvexpand TimeGenerated, IPAddresses, Status
| extend TimeGenerated = todatetime(tostring(TimeGenerated)), IPAddress = tostring(IPAddresses), Status = tostring(Status)
| project-away IPAddresses
| summarize StartTime = min(TimeGenerated), EndTime = max(TimeGenerated) by UserPrincipalName, UserId, UserDisplayName, Status, FailedLogonCount, IPAddress, IPAddressCount, AppDisplayName, Browser, OS, FullLocation
| where (IPAddressCount >= threshold_IPAddressCount and FailedLogonCount >= threshold_Failed) or FailedLogonCount >= threshold_FailedwithSingleIP
| project UserPrincipalName);
OfficeActivity
| where TimeGenerated > ago(time_window)
| where Operation =~ "MemberRoleChanged"
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '2'
| where Members in (failed_signins)
```

<span data-ttu-id="4e9bb-173">Вы также можете сделать обнаружения SigninLogs специфичными для Teams, добавив фильтр только для входов на основе Teams:</span><span class="sxs-lookup"><span data-stu-id="4e9bb-173">Also, you can make the SigninLogs detections specific to Teams by adding a filter for only Teams-based logons by using:</span></span>

```Kusto
| where AppDisplayName has 'Teams'
```

<span data-ttu-id="4e9bb-174">Для дополнительного разъяснения использования *где у AppDisplayName есть Teams* запрос KQL ниже демонстрирует успешный вход с одного IP-адреса и неудачный вход с другого IP-адреса, но ограничен *только* входами в Teams:</span><span class="sxs-lookup"><span data-stu-id="4e9bb-174">To help explain using *where AppDisplayName has Teams* further, the KQL you see below demonstrates a successful logon from one IP address with failure from a different IP address, but scoped to *only* Teams sign-ins:</span></span>

```Kusto
let timeFrame = 1d;
let logonDiff = 10m;
SigninLogs 
  | where TimeGenerated >= ago(timeFrame) 
  | where ResultType == "0" 
  | where AppDisplayName has "Teams"
  | project SuccessLogonTime = TimeGenerated, UserPrincipalName, SuccessIPAddress = IPAddress, AppDisplayName, SuccessIPBlock = strcat(split(IPAddress, ".")[0], ".", split(IPAddress, ".")[1])
  | join kind= inner (
      SigninLogs 
      | where TimeGenerated >= ago(timeFrame) 
      | where ResultType !in ("0", "50140") 
      | where ResultDescription !~ "Other"  
      | where AppDisplayName startswith "Microsoft Teams"
      | project FailedLogonTime = TimeGenerated, UserPrincipalName, FailedIPAddress = IPAddress, AppDisplayName, ResultType, ResultDescription
  ) on UserPrincipalName, AppDisplayName 
  | where SuccessLogonTime < FailedLogonTime and FailedLogonTime - SuccessLogonTime <= logonDiff and FailedIPAddress !startswith SuccessIPBlock
  | summarize FailedLogonTime = max(FailedLogonTime), SuccessLogonTime = max(SuccessLogonTime) by UserPrincipalName, SuccessIPAddress, AppDisplayName, FailedIPAddress, ResultType, ResultDescription 
  | extend timestamp = SuccessLogonTime, AccountCustomEntity = UserPrincipalName, IPCustomEntity = SuccessIPAddress
```

## <a name="important-information-and-updates"></a><span data-ttu-id="4e9bb-175">Важная информация и обновления</span><span class="sxs-lookup"><span data-stu-id="4e9bb-175">Important information and updates</span></span>

<span data-ttu-id="4e9bb-176">**Благодарим за совместную работу над контентом Пита Брайана, Николаса Диколу и Мэтью Лоу.**</span><span class="sxs-lookup"><span data-stu-id="4e9bb-176">**Thank you for content collaboration, Pete Bryan, Nicholas DiCola, and Matthew Lowe.**</span></span> <span data-ttu-id="4e9bb-177">Пит Брайан и люди, с которыми он совместно работает, продолжают разрабатывать запросы обнаружения и поиска для Teams.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-177">Pete Bryan, and people he collaborates with, continue to develop detection and hunting queries for Teams.</span></span>

<span data-ttu-id="4e9bb-178">Оставайтесь на связи с этим репозиторием [Git Hub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) для обновлений.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-178">Stay in touch with this [Git Hub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) repository for updates.</span></span>

<span data-ttu-id="4e9bb-179">Следите за обновлениями для [анализатора](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) и [приложения логики](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data), использовавшихся в этой статье.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-179">Watch for updates to the [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) and [logic app](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) used in this article.</span></span>

<span data-ttu-id="4e9bb-180">Вы также должны присоединиться к [сообществу Azure Sentinel](https://github.com/Azure/Azure-Sentinel/wiki) и участвовать в нем.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-180">You should also join (and contribute to) the [Azure Sentinel community](https://github.com/Azure/Azure-Sentinel/wiki).</span></span> <span data-ttu-id="4e9bb-181">Мы очень ждем отзывы об этой статье, поэтому воспользуйтесь формой обратной связи ниже.</span><span class="sxs-lookup"><span data-stu-id="4e9bb-181">We are actively looking for feedback on this article, so please use the feedback option below.</span></span> <span data-ttu-id="4e9bb-182">Спасибо и удачной охоты на угрозы. </span><span class="sxs-lookup"><span data-stu-id="4e9bb-182">Thank you & Happy hunting.</span></span>

[<span data-ttu-id="4e9bb-183">Регистрация приложения в Azure AD</span><span class="sxs-lookup"><span data-stu-id="4e9bb-183">Registering your application in Azure AD</span></span>](/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[<span data-ttu-id="4e9bb-184">Включение и отключение поиска в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="4e9bb-184">Turn audit log search on or off</span></span>](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)

[<span data-ttu-id="4e9bb-185">Что собой представляет Azure Sentinel?</span><span class="sxs-lookup"><span data-stu-id="4e9bb-185">What is Azure Sentinel?</span></span>](/azure/sentinel/overview)
