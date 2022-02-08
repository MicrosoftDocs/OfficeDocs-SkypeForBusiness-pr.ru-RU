---
title: Управление доступом пользователей к Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: Узнайте, как управлять доступом пользователей к Teams путем назначения или удаления лицензии Teams пользователям в организации.
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0d467e2e3fcdff6e688c13d952f434e635f7d038
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384127"
---
# <a name="manage-user-access-to-teams"></a>Управление доступом пользователей к Teams

Вы управляете доступом Teams пользователями, назначая или удаляя лицензии Microsoft Teams продуктов. За исключением Teams анонимного присоединения к собраниям, у каждого пользователя в организации должна быть Teams лицензия, прежде чем он сможет Teams. Вы можете назначить лицензию Teams новым пользователям при их создания или пользователям с существующими учетными данными.

По умолчанию, когда пользователю назначен план лицензирования (например, Microsoft 365 корпоративный E3 или Microsoft 365 бизнес премиум), ему автоматически назначена лицензия Teams, а пользователю включена Teams. Вы можете отключить или включить Teams для пользователя, удалив или назначив лицензию в любое время.

Используйте политики обмена сообщениями, управляемые в Центре администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams</a>, для управления функциями чата и сообщений каналов, доступными пользователям в Teams. Вы можете использовать политику по умолчанию или создать одну или несколько настраиваемой политики обмена сообщениями для пользователей в организации. Дополнительные узнать об этом можно [в этой](messaging-policies-in-teams.md) Teams.
Вы управляете Teams лицензиями на Центр администрирования Microsoft 365 или с помощью PowerShell. Для управления лицензиями необходимо быть глобальным администратором или администратором управления пользователями.

> [!NOTE]
> Мы рекомендуем включить Teams для всех пользователей, чтобы группы могли быть естественно сформированы для проектов и других динамических инициатив. Даже если вы работаете в пилотном проекте, может быть полезно сохранить Teams для всех пользователей, но только целевое взаимодействие с пилотной группой пользователей.

## <a name="using-the-microsoft-365-admin-center"></a>Использование Центр администрирования Microsoft 365

Teams лицензиями на уровне пользователя управляется непосредственно Центр администрирования Microsoft 365 интерфейсов управления пользователями. Администратор может назначать лицензии для новых пользователей при создании их учетных записей, а также для пользователей с существующими учетными записями. 

> [!IMPORTANT]
> Администратор должен иметь права глобального администратора или администратора управления пользователями для управления Microsoft Teams лицензиями.
Используйте Центр администрирования Microsoft 365 для Teams лицензий отдельных пользователей или небольших наборов пользователей за раз. Вы можете управлять Teams лицензиями на странице Лицензии (одновременно до 20 пользователей) или **На странице Активные** пользователи. Выбор метода зависит от того, хотите ли вы управлять лицензиями на продукты для определенных пользователей или лицензиями пользователей для определенных продуктов.

Если вам нужно управлять лицензиями Teams для большого количества пользователей, например сотен или тысяч пользователей, используйте [PowerShell](#using-powershell) или групповое лицензирование в Azure Active Directory [(Azure AD).](/azure/active-directory/users-groups-roles/licensing-groups-assign). 

### <a name="assign-a-teams-license"></a>Назначение лицензии Teams лицензии

Действия зависят от того, используете ли вы страницу **Лицензии** или **Активные** пользователи.  Пошаговую инструкцию см. в инструкциях по [назначению лицензий пользователям](/microsoft-365/admin/manage/assign-licenses-to-users).

|&nbsp;|&nbsp;|
|---------|---------|
|![Снимок экрана: Teams лицензия для пользователя.](media/assign-teams-licenses-1.png)    | ![Снимок экрана: Teams лицензии пользователя](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>Удаление лицензии Teams лицензии

> [!IMPORTANT]
> На отключение SKU Teams около 24 часов.

При Teams лицензии пользователя приложение Teams отключено и больше не будет Teams в приложении или на домашней странице. Подробные инструкции см. в описании отзыва [лицензий у пользователей](/microsoft-365/admin/manage/remove-licenses-from-users).

|&nbsp;|&nbsp;|
|---------|---------|
|![Снимок экрана: 1 лицензия Teams отключена для пользователя.](media/remove-teams-licenses-1.png)    | ![Снимок экрана: 2 лицензия Teams отключена для пользователя](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>С помощью PowerShell

Используйте PowerShell для массовой Teams лицензий для пользователей. Вы включаете и отключая Teams powerShell так же, как и для любой другой лицензии на план обслуживания. Вам нужны идентификаторы планов обслуживания для Teams:

- Microsoft Teams: TEAMS1
- Microsoft Teams для GCC: TEAMS_GOV
- Microsoft Teams для DoD: TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>Массовое Teams лицензий

Подробные инструкции см. в [описании назначения лицензий учетным записям пользователей с помощью PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="remove-teams-licenses-in-bulk"></a>Массовое Teams лицензий

Подробные инструкции см. в инструкциях Отключение доступа к службам с помощью [PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) и Отключение доступа к службам при [назначении пользовательских лицензий](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).

#### <a name="example"></a>Пример 

Ниже приводится пример использования [msolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) и [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) для отключения Teams для пользователей с определенным планом лицензирования. Например, выполните эти действия, чтобы сначала отключить Teams для всех пользователей с определенным планом лицензирования. Затем в Teams для каждого отдельного пользователя, которому должен быть доступ к Teams.

> [!IMPORTANT]
> С [помощью msolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) можно включить все службы, которые ранее были отключены, если они не были явно определены в настраиваемом сценарии. Например, если вы хотите оставить отключенными Exchange и Sway, одновременно отключив Teams, необходимо включить его в сценарий, иначе для этих пользователей будут включены Exchange и Sway.

Чтобы отобразить все доступные планы лицензирования в организации, запустите следующую команду: Дополнительные действия см. в этом обзоре [лицензий и служб с помощью PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).


```powershell
Get-MsolAccountSku
```

Запустите следующие команды, в которых указаны название вашей организации и идентификатор плана лицензирования, \<CompanyName:License> который вы извлекли на более ранней этапе. Например, ContosoSchool:ENTERPRISEPACK_STUDENT.

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

Чтобы отключить Teams для всех пользователей, у которых есть активная лицензия для плана лицензирования, следуя следующей команде:

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a>Статьи по теме

- [Teams надстройки](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Назначение Teams надстройки](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [Просмотр лицензий и служб с помощью PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Названия продуктов и идентификаторы планов служб для лицензирования](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Справка по SKU для образования](sku-reference-edu.md)
