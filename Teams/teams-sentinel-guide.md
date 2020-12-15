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
ms.openlocfilehash: 6aa8e733aeb3828bb1815001ba0299a9ee1aaf78
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852150"
---
# <a name="azure-sentinel-and-microsoft-teams"></a>Azure Sentinel и Microsoft Teams

Teams играет центральную роль как во взаимодействии, так и в распространении данных в облаке Microsoft 365. Так как служба Teams связана со многими базовыми технологиями в облаке, она может использовать преимущества человеческого и автоматизированного анализа не только при *поиске в журналах*, но и при *отслеживании собраний в реальном времени*. Azure Sentinel предлагает эти решения администраторам.

> [!NOTE]
> Требуется освежить знания по Azure Sentinel? [Эта статья](https://docs.microsoft.com/azure/sentinel/overview) как раз для этого.

## <a name="sentinel-and-microsoft-teams-activity-logs"></a>Sentinel и журналы действий Microsoft Teams

В этой статье рассматривается сбор журналов действий Teams в Azure Sentinel. Помимо предоставления администраторам возможности управления безопасностью в одном месте (включая любые выбранные сторонние устройства, Защиту от угроз (Майкрософт) и другие рабочие нагрузки Microsoft 365), книги Sentinel и runbook позволяют систематизировать мониторинг безопасности. Хорошим первым шагом в этом процессе является сбор необходимых журналов для анализа.

> [!NOTE]
> В одном экземпляре Azure Sentinel можно использовать несколько подписок на Microsoft 365. Это позволит выполнять [отслеживание в реальном времени](https://docs.microsoft.com/azure/sentinel/livestream) и обнаруживать угрозы в архивных файлах журнала. Администраторы смогут выполнять поиск, используя [запросы в разных ресурсах](https://docs.microsoft.com/azure/azure-monitor/log-query/cross-workspace-query), в одной группе ресурсов, в разных группах ресурсов или в другой подписке.

## <a name="step-1-collect-teams-logs"></a>Шаг 1. Сбор журналов Teams

Этот раздел состоит из трех частей:

1. Включение журналов аудита в **Microsoft 365** (M365).
2. Регистрация приложения в **Microsoft Azure**, чтобы разрешить проверку подлинности и авторизацию для сбора журналов.
3. Регистрация подписки на API, которая позволит осуществлять сбор журналов через API M365 посредством **PowerShell**.

### <a name="enable-audit-logs-in-m365"></a>Включение журналов аудита в M365

Так как Teams регистрирует действия через M365, журналы аудита не собираются по умолчанию. Включите эту функцию с помощью [этих действий](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0). Данные Teams собираются для аудита M365 в разделе *Audit.General*.

### <a name="register-an-app-in-microsoft-azure-for-log-collection"></a>Регистрация приложения в Microsoft Azure для сбора журналов

> [!TIP]
> Перед началом вам потребуется записать ваш **идентификатор приложения/идентификатор клиента** и **идентификатор клиента** для использования в дальнейшем. Запишите их при выполнении действий регистрации приложения ниже. Вы увидите оба идентификатора.
>- После создания приложения щелкните "Регистрация приложений" на боковой панели быстрого запуска, найдите отображаемое имя вашего нового приложения и скопируйте идентификатор приложения (клиент).
>- Щелкните "Обзор" на боковой панели быстрого запуска и скопируйте идентификатор каталога (клиент).

Проверьте подлинность и авторизуйте приложение Azure Active Directory (Azure AD) для сбора данных журналов из API.

1. Перейдите в колонку *Azure AD* на портале Azure.
2. На боковой панели быстрого запуска щелкните *Регистрация приложений*.
3. Выберите *Новая регистрация*.
4. Назовите свое приложение для сбора журналов Teams и нажмите *Зарегистрировать*.
5. Последовательно выберите *Разрешения API* > *Добавить разрешение* > *Office 365 Management APIs* > *Разрешения приложения*.
6. Разверните раздел "Веб-канал активности" и установите флажок *ActivityFeed.Read*.
7. Выберите здесь *Предоставить согласие администратора*. Щелкните "Да" при появлении запроса на подтверждение.
8. Щелкните *Сертификаты и секреты* на боковой панели и нажмите кнопку *Новый секрет клиента*.
9. В окне "Добавить секрет клиента" введите описание нового секрета клиента, выберите "Никогда" для истечения срока действия и нажмите *Добавить*.

> [!IMPORTANT]
> **Очень важно** скопировать новый секрет клиента в запись диспетчера паролей под именем созданного приложения. Вы не сможете вернуться для просмотра этого секрета после закрытия колонки Azure (*колонка* — это термин Azure, обозначающий окно).

### <a name="register-the-api-with-powershell-to-collect-teams-logs"></a>Регистрация API с помощью PowerShell для сбора журналов Teams

Завершающее действие настройки — получение и регистрация подписки на API, чтобы можно было собирать данные журналов. Это выполняется с помощью вызовов REST PowerShell в API действий управления M365.

Будьте готовы указать значения **идентификатора приложения (клиент)**, нового **секрета клиента**, вашего **домена URL-адреса для M365** и **идентификатора каталога (клиент)** в командлете PowerShell ниже.

```PowerShell
$ClientID = "<Application (client) ID>"  
$ClientSecret = "<Client secret>"  
$loginURL = "https://login.microsoftonline.com/"  
$tenantdomain = "<domain>.onmicrosoft.com"  

$TenantGUID = "<Directory (tenant) ID>"  
$resource = "https://manage.office.com"  
$body = @{grant_type="client_credentials";resource=$resource;client_id=$ClientID;client_secret=$ClientSecret}
$oauth = Invoke-RestMethod -Method Post -Uri $loginURL/$tenantdomain/oauth2/token?api-version=1.0 -Body $body  
$headerParams = @{'Authorization'="$($oauth.token_type) $($oauth.access_token)"}
$publisher = New-Guid
Invoke-WebRequest -Method Post -Headers $headerParams -Uri "https://manage.office.com/api/v1.0/$tenantGuid/activity/feed/subscriptions/start?contentType=Audit.General&PublisherIdentifier=$Publisher"
```

## <a name="step-2-deploy-a-sentinel-playbook-to-ingest-the-teams-logs"></a>Шаг 2. Развертывание сборника схем Sentinel для приема журналов Teams

Сборники схем Azure Sentinel (также называемые приложениями логики) позволяют Azure принимать ваши собранные данные Teams. Приложение логики опрашивает Office 365, чтобы найти данные аудита, записываемые в рабочую область Azure Sentinel.

Используйте [этот](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) шаблон ARM, чтобы развернуть сборник схем Sentinel.

Вот о чем нужно помнить:

1. Вам потребуется просмотреть шаблон ARM и определенные значения заменить значениями, соответствующими вашей среде.
2. Вам требуется предусмотреть время между приемом журналов и просмотром результатов в Azure Sentinel.

   Подождите 5–10 минут, учитывая, что если в течение последних 5 минут данные отсутствуют, отобразится сообщение об ошибке. Проверьте журналы аудита и имейте в виду, что в используемых системах результаты должны отображаться в течение 5–10 минут, так как сведения Teams находятся в событиях Audit.General, собирающих больше данных, чем журналы Teams. При использовании текстовой среды обязательно применяйте Teams, чтобы создавать журналы.

![Рисунок с классами приложений логики.](media/tracyp-teams-sentinel-logic-app.png#thumbnail)

 <p><details><summary> Объяснение действий на рисунке: 
  </summary>

  • Повторение — это триггер приложения логики, указывающий рабочему процессу необходимость запуска каждый час.
  <p>
• Действие "Текущее время" очень простое и заключается в получении текущего времени.
  <p>
• Инициализация переменной создает переменную NextPage и присваивает ей значение 1. Это будет применено позже, чтобы обработать разбивку на страницы из API Office 365.
  <p>
• Инициализация переменной 2 создает пустую переменную "Start Time".
  <p>
• Выполнение запроса и перечисление результатов — это действие Azure Monitor, запрашивающее в рабочей области последний журнал O365, введенный из приложения логики.
  <p>
• Условие 4 используется, чтобы проверить, возвратил ли запрос "Выполнение запроса и перечисление результатов" какие-либо данные. Это выполняется, чтобы проверить, впервые ли использовано приложение логики. Если данные не возвращаются, переменной StartTime присваивается значение Now — 24 часа. Если данные возвращаются, переменной StartTime присваивается значение последней записи TimeGenerated. Это делается для того, чтобы запрос мог получить данные от последней записи до текущего момента в опросе API Office 365 или за последние 24 часа, если это первый запуск.
  <p>
• Инициализация переменной 3 создает переменную AvailableUri. Это строка с URL-адресом, созданная с использованием StartTime и CurrentTime в качестве времени начала и окончания соответственно.
  <p>
• Условие Until — это цикл, позволяющий приложению логики продолжать опрашивать API, чтобы проверять наличие дополнительных данных (разбивка на страницы). Пока переменная NextPage имеет значение 1, цикл продолжается. Позже эта переменная будет обновлена, если закончатся страницы для получения.
  <p>
• В цикле Until первый шаг HTTP подключается к AvailableURI. Этот URI возвращает список доступного содержимого и URI каждого элемента содержимого. Дополнительные сведения об этих принципах работы см. по URL-адресу https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.
  <p>
• Далее выполняется проверка, чтобы убедиться в возвращении данных. Условие проверяет, равна ли длина текста 0. Если это так, данные для записи в аналитику журнала отсутствуют. Если значение больше 0, существуют данные для обработки.
  <p>
• Если данные обнаружены, их требуется обработать. Анализ JSON определяет схему возвращаемых данных. Это позволяет приложениям логики использовать проанализированные данные в качестве динамического контента в последующих действиях.
  <p>
• Так как возвращаемый список доступных данных является массивом, используется действие For Each для циклического перебора списка доступных элементов содержимого.
  <p>
• Затем захватывается содержимое.  Вновь используется параметр HTTP для получения contentUri (динамическое свойство, созданное из анализа JSON), являющегося URL-адресом получаемых данных.
  <p>
• Анализ JSON также используется для синтаксического анализа возвращаемых данных. Некоторые примеры содержимого доступны по URL-адресу https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.
  <p>
• Возвращаемые данные также являются массивом. Здесь также можно использовать цикл For Each. В этом цикле рабочий процесс получает текущий элемент данных и использует действие Send Data для записи данных в аналитику журнала.
  <p>
• Так как в доступном содержимом может быть несколько страниц, условие проверяет, что параметру NextPageUri не присвоено значение NULL. Если он имеет значение NULL, параметру NextPage присваивается значение 0, что завершает цикл Until. Если в нем есть URL-адрес, переменная AvaibleUri обновляется с использованием этого URL-адреса. В этом случае при следующем запуске цикла Until используется следующий доступный URL-адрес, а не начальный URL-адрес.

  </details>

> [!TIP]
> Вместо этого вы можете использовать *функцию Azure*, чтобы принять эти журналы. В этом случае см. сведения о развертывании [здесь](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data) или [здесь](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp) в зависимости от предпочтений.

При запущенном соединителе (независимо от выбранных выше вариантов) вы должны увидеть настраиваемую таблицу O365API_CL в рабочей области Azure Sentinel. В ней размещаются ваши журналы Teams.

## <a name="step-3-use-sentinel-to-monitor-microsoft-teams"></a>Шаг 3. Использование Sentinel для мониторинга Microsoft Teams

Удостоверение — это важный для отслеживания вектор атаки, связанный с Microsoft Teams. Так как Azure Active Directory (Azure AD) — это основа каталога Microsoft 365, включая Teams, сбор и поиск в журналах Azure AD угроз, связанных с проверкой подлинности, облегчает выявление подозрительных действий в отношении удостоверений. Вы можете использовать встроенный соединитель для извлечения данных Azure AD в Azure Sentinel, а также использовать эти запросы [обнаружения](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) и [поиска](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) для выявления проблем.

В отношении специфичных для Microsoft Teams атак, например угроз для данных, в Azure Sentinel также имеются средства для их отслеживания и поиска.

### <a name="create-a-parser-for-your-data"></a>Создание средства синтаксического анализа для данных

Первое, что нужно сделать, чтобы разобраться в большом наборе собранных данных, — понять их значение с помощью синтаксического анализа. Это осуществляется с помощью функции языка запросов Kusto (KQL), упрощающей работу с данными.

> [!NOTE]
> Функции KQL — это запросы KQL, сохраненные в виде данных под названием "функция". Функции KQL содержат псевдоним, который можно ввести в поле запроса в Sentinel, чтобы быстро повторить запрос. Дополнительные сведения о функциях KQL и создании функции синтаксического анализа см. в [этой статье сообщества Tech Community](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).
 
 Средство синтаксического анализа ниже — это настраиваемый пример, предназначенный для выбора подмножества полей API управления Office 365, относящихся к *Teams*. Также существует предлагаемое средство синтаксического анализа [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt), но в примере ниже можно вносить изменения для соблюдения различных потребностей и предпочтений.

```kusto
O365API_CL
| where Workload_s =~ "MicrosoftTeams"
| project TimeGenerated,
          Workload=Workload_s,
          Operation=Operation_s,
          TeamName=columnifexists('TeamName_s', ""),
          UserId=columnifexists('UserId_s', ""),
          AddOnName=columnifexists('AddOnName_s', AddOnGuid_g),
          Members=columnifexists('Members_s', ""),
          Settings=iif(Operation_s contains "Setting", pack("Name", columnifexists('Name_s', ""), "Old Value", columnifexists('OldValue_s', ""), "New Value", columnifexists('NewValue_s', "")),""),
          Details=pack("Id", columnifexists('Id_g', ""),  "OrganizationId", columnifexists('OrganizationId_g', ""), "UserType", columnifexists('UserType_d', ""), "UserKey", columnifexists('UserKey_g', ""), "TeamGuid", columnifexists('TeamGuid_s', "")) 
```
 Сохраните средство синтаксического анализа как функцию KQL с псевдонимом TeamsData. Она будет использоваться в последующих запросах. Сведения о настройке и использовании функции KQL в качестве средства синтаксического анализа, можно найти в этой [статье сообщества Tech Community](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).

## <a name="helpful-hunting-kql-queries"></a>Полезные запросы KQL для поиска

Используйте эти запросы, чтобы познакомиться с данными и средой Teams. Понимание среды и ее поведения — это отличный первый шаг по выявлению подозрительных действий. После этого вы можете перейти к поиску угроз.

#### <a name="federated-external-users-query"></a>Запросы федеративных внешних пользователей

Получите список сайтов Teams с федеративными внешними пользователями. У этих пользователей будет доменное имя или суффикс UPN, *не* принадлежащие вашей организации. В этом примере запроса организации принадлежит домен contoso.com.

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| extend UPN = tostring(parse_json(Members)[0].Upn)
| where UPN !endswith "contoso.com"
| where parse_json(Members)[0].Role == 3
| project TeamName, Operation, UserId, Members, UPN
```

> [!TIP]
> Дополнительные сведения о внешнем и гостевом типах доступа в Teams см. в [этой статье](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations) или в разделе *Типы участников* в [руководстве по безопасности Teams](https://docs.microsoft.com/microsoftteams/teams-security-guide).

#### <a name="who-recently-joined--whose-role-changed"></a>Кто недавно присоединился или чья роль изменена

Запросите определенного пользователя, чтобы проверить, был ли он добавлен в канал Teams за последние 7 дней или в течение недели:

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members contains "UserName"
```

Изменилась ли роль пользователя в команде за последние 7 дней:

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| where Members contains "Role" and Members contains "1"
```

#### <a name="external-users-from-unknown-or-new-organizations"></a>Внешние пользователи из неизвестных или новых организаций

В Teams вы можете добавлять внешних пользователей в среду или каналы. Организации часто имеют ограниченное количество ключевых партнеров и добавляют пользователей этих партнеров. Эта функция KQL ищет добавленных в команды внешних пользователей из организаций, которые раньше отсутствовали или не добавлялись.

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
// If you want to look at users further back than the last day change this value 
let lookback_data = 1d; 
let known_orgs = ( 
TeamsData  
| where TimeGenerated > ago(data_date) 
| where Operation =~ "MemberAdded" or Operation =~ "TeamsSessionStarted" 
// Extract the correct UPN and parse our external organization domain 
| extend UPN = iif(Operation == "MemberAdded", tostring(parse_json(Members)[0].UPN), UserId) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| summarize by Organization); 
TeamsData  
| where TimeGenerated > ago(lookback_data) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| where Organization !in (known_orgs) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UPN 
```

#### <a name="external-users-who-were-added-and-then-removed"></a>Внешние пользователи, которые были добавлены, а затем удалены

Злоумышленники с определенным уровнем доступа могут добавить новую внешнюю учетную запись в Teams, чтобы получить доступ и извлечь данные. Они также могут быстро удалить этого пользователя, чтобы скрыть получение доступа. Этот запрос используется для поиска внешних учетных записей, которые добавлены в Teams и быстро удалены, чтобы выявить подозрительное поведение.

```kusto
// If you want to look at user added further than 7 days ago adjust this value 
let time_ago = 7d; 
// If you want to change the timeframe of how quickly accounts need to be added and removed change this value 
let time_delta = 1h; 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeAdded=TimeGenerated, Operation, UPN, UserWhoAdded = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid) 
| join ( 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberRemoved" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeDeleted=TimeGenerated, Operation, UPN, UserWhoDeleted = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid)) on UPN, TeamGuid 
| where TimeDeleted < (TimeAdded + time_delta) 
| project TimeAdded, TimeDeleted, UPN, UserWhoAdded, UserWhoDeleted, TeamName, TeamGuid 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeAdded, AccountCustomEntity = UPN 
```

#### <a name="new-bot-or-application-added"></a>Добавлен новый бот или приложение

В Teams можно добавлять приложения или ботов для команды, чтобы расширить набор функций. Сюда относятся пользовательские приложения и боты. В некоторых случаях приложение или бот могут использоваться для создания присутствия в Teams без необходимости пользовательской учетной записи, а также могут обращаться к файлам и другим данным. Этот запрос используется для поиска новых приложений и ботов в Teams.

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
let historical_bots = ( 
TeamsData 
| where TimeGenerated > ago(data_date) 
| where isnotempty(AddOnName) 
| project AddOnName); 
TeamsData 
| where TimeGenerated > ago(1d) 
// Look for add-ins we have never seen before 
| where AddOnName in (historical_bots) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UserId 
```

#### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a>Учетные записи пользователей, являющихся владельцами большого количества команд

Злоумышленники, пытающиеся получить дополнительные права, могут назначать себе права владельцев большого количества разнообразных команд, а пользователи обычно создают и владеют небольшим количеством команд, посвященных определенным темам. Этот запрос KQL ищет подозрительные действия.

```kusto
// Adjust this value to change how many teams a user is made owner of before detecting 
let max_owner_count = 3; 
// Change this value to adjust how larger timeframe the query is run over. 
let time_window = 1d; 
let high_owner_count = (TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| summarize dcount(TeamName) by Member 
| where dcount_TeamName > max_owner_count 
| project Member); 
TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| where Member in (high_owner_count) 
| extend TeamGuid = tostring(Details.TeamGuid) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = Member 
```

#### <a name="many-team-deletions-by-a-single-user"></a>Удаление большого количества команд одним пользователем

Злоумышленники могут вызывать нарушения в работе и создавать угрозы проектам и данным, удаляя несколько команд. Так как команды обычно удаляются отдельными владельцами, централизованное удаление нескольких команд может быть признаком проблемы. Этот запрос KQL ищет отдельных пользователей, удаляющих несколько команд.

```kusto
 // Adjust this value to change how many Teams should be deleted before including
 let max_delete = 3;
 // Adjust this value to change the timewindow the query runs over
 let time_window = 1d;
 let deleting_users = (
 TeamsData 
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | summarize count() by UserId
 | where count_ > max_delete
 | project UserId);
 TeamsData
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | where UserId in (deleting_users)
 | extend TeamGuid = tostring(Details.TeamGuid)
 | project-away AddOnName, Members, Settings
 // Uncomment the following line to map query entities is you plan to use this as a detection query
 //| extend timestamp = TimeGenerated, AccountCustomEntity = UserId
```

#### <a name="expanding-your-thread-hunting-opportunities"></a>Расширение возможностей поиска цепочек

Вы можете расширить поиск, объединив запросы из таких ресурсов, как Azure Active Directory (Azure AD) или других рабочих нагрузок Office 365, с запросами Teams. Одним из примеров является объединенное обнаружение подозрительных закономерностей в Azure AD SigninLogs и использование этих сведений при поиске владельцев команд.

```kusto
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
TeamsData
| where TimeGenerated > ago(time_window)
| where Operation =~ "MemberRoleChanged"
| extend Member = tostring(parse_json(Members)[0].UPN) 
| extend NewRole = toint(parse_json(Members)[0].Role) 
| where NewRole == 2
| where Member in (failed_signins)
| extend TeamGuid = tostring(Details.TeamGuid)
```

Вы также можете сделать обнаружения SigninLogs специфичными для Teams, добавив фильтр только для входов Teams:

```kusto
| where AppDisplayName startswith "Microsoft Teams"
```

Для дополнительного разъяснения использования `where AppDisplayName starts with "Microsoft Teams"` запрос KQL ниже демонстрирует успешный вход с одного IP-адреса и неудачный вход с другого IP-адреса применительно только ко входам Teams:

```kusto
let timeFrame = 1d;
let logonDiff = 10m;
SigninLogs 
  | where TimeGenerated >= ago(timeFrame) 
  | where ResultType == "0" 
  | where AppDisplayName startswith "Microsoft Teams"
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

**Благодарим за совместную работу над контентом Пита Брайана, Николаса Диколу и Мэтью Лоу.** Пит Брайан и люди, с которыми он совместно работает, продолжат разрабатывать запросы обнаружения и поиска для Teams, поэтому проверяйте обновления в этом репозитории [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs).  Отслеживайте обновления для [средства синтаксического анализа](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) и [приложений логики](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data), использовавшихся в этой статье. Вы также можете присоединиться к [сообществу Azure Sentinel](https://github.com/Azure/Azure-Sentinel/wiki) и участвовать в нем. Спасибо! Удачного поиска.

[Регистрация приложения в Azure AD](https://docs.microsoft.com/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[Включение и отключение поиска в журнале аудита](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0)

[Что такое Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)
