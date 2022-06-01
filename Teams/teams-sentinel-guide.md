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
ms.localizationpriority: high
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
ms.openlocfilehash: 1cf7d4e9670d8ea282105eaa057347fa7e9f6dac
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2022
ms.locfileid: "65822998"
---
# <a name="azure-sentinel-and-microsoft-teams"></a>Azure Sentinel и Microsoft Teams

> [!IMPORTANT]
> Теперь у Azure Sentinel есть интегрированный соединитель. Дополнительные сведения см. в статье [Подключение журналов Office 365 к Azure Sentinel](/azure/sentinel/connect-office-365). Таков рекомендуемый метод для сбора этих журналов; он заменяет собой методы сбора, описанные ниже.

Teams играет центральную роль во взаимодействии и распространении данных в облаке Microsoft 365. Так как служба Teams связана со многими базовыми технологиями в облаке, она может использовать преимущества человеческого и автоматизированного анализа. Это относится как к *поиску в журналах*, так и *при отслеживании собраний в режиме реального времени*. Azure Sentinel предлагает эти решения администраторам.

> [!NOTE]
> Требуется освежить знания по Azure Sentinel? [Эта статья](/azure/sentinel/overview) как раз для этого.

## <a name="sentinel-and-microsoft-teams-activity-logs"></a>Sentinel и журналы действий Microsoft Teams

В этой статье рассматривается сбор журналов действий Teams в Azure Sentinel.

Sentinel позволяет администраторам управлять безопасностью в одном месте. Это включает в себя управление:

- Сторонними устройствами
- Защита от угроз (Майкрософт)
- Рабочими нагрузками Microsoft 365

Книги Sentinel и модули Runbook могут сделать мониторинг безопасности *системным*. Хорошим первым шагом в этом процессе является сбор необходимых журналов для анализа.

> [!NOTE]
> В одном экземпляре Azure Sentinel можно использовать несколько подписок на Microsoft 365. Это позволит выполнять [отслеживание в режиме реального времени](/azure/sentinel/livestream) и обнаруживать угрозы в архивных файлах журнала. Администраторы смогут выполнять поиск, используя [запросы в разных ресурсах](/azure/azure-monitor/log-query/cross-workspace-query), в одной группе ресурсов, в разных группах ресурсов или в другой подписке.

## <a name="step-1-collect-teams-logs-enable-audit-logs-in-microsoft-365"></a>Шаг 1. Сбор журналов Teams: включение журналов аудита в Microsoft 365

Так как Teams регистрирует действия через Microsoft 365, журналы аудита не собираются по умолчанию. Эту функцию можно включить, выполнив [следующие шаги](/microsoft-365/compliance/turn-audit-log-search-on-or-off). Данные Teams собираются для аудита Microsoft 365 в разделе *Audit.General*.

## <a name="step-2-connect-office-365-logs-to-azure-sentinel"></a>Шаг 2. Подключение журналов Office 365 к Azure Sentinel

Azure Sentinel предоставляет встроенный соединитель для журналов Office 365, который позволяет принимать данные Teams в Azure Sentinel вместе с другими данными Office 365.
 
В Azure Sentinel включите соединитель данных Office 365. Для получения дополнительной информации см. раздел [Документация Azure Sentinel](/azure/sentinel/connect-office-365).

## <a name="helpful-hunting-kql-queries"></a>Полезные запросы KQL для поиска

Используйте эти запросы, чтобы познакомиться с данными и средой Teams. Понимание среды и ее поведения — это отличный первый шаг по выявлению подозрительных действий. После этого вы можете перейти к поиску угроз.

### <a name="federated-external-users-query"></a>Запросы федеративных внешних пользователей

Получите список сайтов Teams с федеративными внешними пользователями. У этих пользователей есть доменное имя и/или суффикс UPN, которые не принадлежат вашей организации.

В этом примере запроса организации принадлежит домен contoso.com.

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
> Дополнительные сведения о внешнем и гостевом типах доступа в Teams см. в разделе [Общение с пользователями из других организаций](communicate-with-users-from-other-organizations.md) или в разделе [Типы участников](teams-security-guide.md#participant-types) в руководстве по безопасности Teams.

### <a name="who-recently-joined--whose-role-changed"></a>Кто недавно присоединился или чья роль изменена

Запросите определенного пользователя, чтобы проверить, был ли он добавлен в канал Teams за последние 7 дней или в течение недели:

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members has "<DisplayName>" or Members has "<UserPrincipalName>"
| project TeamName, Operation, UserId, Members
```

Сделайте запрос о том, изменилась ли роль пользователя в команде за последние 7 дней:

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '1'
``` 

### <a name="external-users-from-unknown-or-new-organizations"></a>Внешние пользователи из неизвестных или новых организаций

В Teams вы можете добавлять внешних пользователей в среду или каналы. Организации часто имеют ограниченное количество ключевых партнеров и добавляют пользователей этих партнеров. Эта функция KQL ищет добавленных в команды внешних пользователей из организаций, которые раньше отсутствовали или не добавлялись.

Дополнительные сведения см. в запросе в [GitHub сообщества Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml).

### <a name="external-users-who-were-added-and-then-removed"></a>Внешние пользователи, которые были добавлены, а затем удалены

Злоумышленники с определенным уровнем доступа могут добавить новую внешнюю учетную запись в Teams, чтобы получить доступ и извлечь данные. Они также могут быстро удалить этого пользователя, чтобы скрыть получение доступа. Этот запрос используется для поиска внешних учетных записей, которые добавлены в Teams и быстро удалены, чтобы выявить подозрительное поведение.

Дополнительные сведения см. в запросе в [GitHub сообщества Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml).

### <a name="new-bot-or-application-added"></a>Добавлен новый бот или приложение

Teams может включать приложения или ботов в команду для расширения набора функций (включая пользовательские приложения и боты). В некоторых случаях приложение или бот могут использоваться для *сохраняемости* в Teams без необходимости учетной записи пользователя, а также могут получать доступ к файлам и другим данным. Этот запрос используется для поиска новых приложений и ботов в Teams.

Дополнительные сведения см. в запросе в [GitHub сообщества Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml).

### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a>Учетные записи пользователей, являющихся владельцами большого количества команд

Злоумышленники, пытающиеся получить дополнительные права, могут назначать себе права владельцев большого количества разнообразных команд. *Обычно* пользователи создают и владеют несколькими командами, посвященным определенным темам. Этот запрос KQL ищет подозрительные действия.

Дополнительные сведения см. в запросе в [GitHub сообщества Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml).

### <a name="many-team-deletions-by-a-single-user"></a>Удаление большого количества команд одним пользователем

Злоумышленники могут вызывать нарушения в работе и создавать угрозы проектам и данным, удаляя несколько команд. Так как команды обычно удаляются отдельными владельцами, централизованное удаление нескольких команд может быть признаком проблемы. Этот запрос KQL ищет отдельных пользователей, удаляющих несколько команд.

Дополнительные сведения см. в запросе в [GitHub сообщества Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml).

### <a name="expanding-your-threat-hunting-opportunities"></a>Расширение возможностей охоты на угрозы

Объединение запросов из таких ресурсов, как Azure Active Directory (Azure AD) или других рабочих нагрузок Office 365, можно использовать с запросами Teams. Например, объедините обнаружение подозрительных шаблонов в Azure AD SigninLogs и используйте эти выходные данные при поиске владельцев групп.

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

Вы также можете сделать обнаружения SigninLogs специфичными для Teams, добавив фильтр только для входов на основе Teams:

```Kusto
| where AppDisplayName has 'Teams'
```

Для дополнительного разъяснения использования *где у AppDisplayName есть Teams* запрос KQL ниже демонстрирует успешный вход с одного IP-адреса и неудачный вход с другого IP-адреса, но ограничен *только* входами в Teams:

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

## <a name="important-information-and-updates"></a>Важная информация и обновления

**Благодарим за совместную работу над контентом Пита Брайана, Николаса Диколу и Мэтью Лоу.** Пит Брайан и люди, с которыми он совместно работает, продолжают разрабатывать запросы обнаружения и поиска для Teams.

Оставайтесь на связи с этим репозиторием [Git Hub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/) для обновлений.

Следите за обновлениями для [анализатора](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) и [приложения логики](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data), использовавшихся в этой статье.

Вы также должны присоединиться к [сообществу Azure Sentinel](https://github.com/Azure/Azure-Sentinel/wiki) и участвовать в нем. Мы очень ждем отзывы об этой статье, поэтому воспользуйтесь формой обратной связи ниже. Спасибо и удачной охоты на угрозы. 

[Регистрация приложения в Azure AD](/skype-sdk/trusted-application-api/docs/registrationinazureactivedirectory)

[Включение и отключение поиска в журнале аудита](/microsoft-365/compliance/turn-audit-log-search-on-or-off)

[Что собой представляет Azure Sentinel?](/azure/sentinel/overview)
