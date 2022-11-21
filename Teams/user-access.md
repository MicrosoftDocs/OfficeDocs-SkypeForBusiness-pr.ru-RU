---
title: Управление доступом пользователей к Microsoft Teams
manager: SerdarSoysal
author: DaniEASmith
ms.author: danismith
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: Узнайте, как управлять доступом пользователей к Teams путем назначения или удаления лицензии Teams для пользователей в вашей организации.
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1ece44c5adf6d1c23a500988c84f813e438927b0
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2022
ms.locfileid: "69130898"
---
# <a name="manage-user-access-to-teams"></a>Управление доступом пользователей к Teams

Вы управляете доступом к Teams на уровне пользователя, назначая или удаляя лицензию на продукт Microsoft Teams. За исключением анонимного присоединения к собраниям Teams, каждый пользователь в вашей организации должен иметь лицензию Teams, прежде чем он сможет использовать Teams. Вы можете назначить лицензию Teams новым пользователям при создании новых учетных записей пользователей или пользователям с существующими учетными записями.

По умолчанию, когда пользователю назначается план лицензирования (например, Microsoft 365 корпоративный E3 или Microsoft 365 бизнес премиум), лицензия Teams назначается автоматически, и пользователь включается для Teams. Вы можете отключить или включить Teams для пользователя, удалив или назначив лицензию в любое время.

Используйте политики обмена сообщениями, управляемые из <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Центра Администратор Teams</a>, чтобы управлять функциями обмена сообщениями в чатах и каналах, доступных пользователям в Teams. Вы можете использовать политику по умолчанию или создать одну или несколько настраиваемых политик обмена сообщениями для пользователей в организации. Дополнительные сведения см. [в статье Управление политиками обмена сообщениями в Teams](messaging-policies-in-teams.md).
Вы управляете лицензиями Teams в Центр администрирования Microsoft 365 или с помощью PowerShell. Для управления лицензиями необходимо быть глобальным администратором или администратором управления пользователями.

> [!NOTE]
> Мы рекомендуем включить Teams для всех пользователей, чтобы команды могли быть органично сформированы для проектов и других динамических инициатив. Даже если вы используете пилотный проект, все равно может быть полезно сохранить teams включенным для всех пользователей, но только целевые сообщения с пилотной группой пользователей.

## <a name="using-the-microsoft-365-admin-center"></a>Использование Центр администрирования Microsoft 365

Лицензии на уровне пользователей Teams управляются непосредственно через интерфейсы управления пользователями Центр администрирования Microsoft 365. Администратор может назначать лицензии для новых пользователей при создании их учетных записей, а также для пользователей с существующими учетными записями.

> [!IMPORTANT]
> Администратор должен иметь права глобального администратора или администратора управления пользователями для управления лицензиями Microsoft Teams.
Используйте Центр администрирования Microsoft 365 для управления лицензиями Teams для отдельных пользователей или небольших наборов пользователей одновременно. Вы можете управлять лицензиями Teams на странице **Лицензии** (одновременно для 20 пользователей) или на странице **Активные пользователи** . Выбор метода зависит от того, хотите ли вы управлять лицензиями на продукты для определенных пользователей или пользовательскими лицензиями для определенных продуктов.

Если вам нужно управлять лицензиями Teams для большого числа пользователей, например сотен или тысяч пользователей, [используйте PowerShell](#using-powershell) или [групповое лицензирование в Azure Active Directory (Azure AD).](/azure/active-directory/users-groups-roles/licensing-groups-assign) 

### <a name="assign-a-teams-license"></a>Назначение лицензии Teams

Действия различаются в зависимости от того, используете ли вы страницу **"Лицензии"** или " **Активные пользователи** ".  Пошаговые инструкции см. в статье [Назначение лицензий пользователям](/microsoft-365/admin/manage/assign-licenses-to-users).

|&nbsp;|&nbsp;|
|---------|---------|
|![Снимок экрана 1: лицензия Teams включена для пользователя.](media/assign-teams-licenses-1.png)    | ![Снимок экрана 2: лицензия Teams включена для пользователя](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>Удаление лицензии Teams

> [!IMPORTANT]
> Отключение SKU Teams вступает в силу около 24 часов.

При удалении лицензии Teams у пользователя teams для этого пользователя отключается, и он больше не будет видеть Teams в средстве запуска приложений или на домашней странице. Подробные инструкции см. в разделе [Отмена назначения лицензий от пользователей](/microsoft-365/admin/manage/remove-licenses-from-users).

|&nbsp;|&nbsp;|
|---------|---------|
|![Снимок экрана 1: лицензия Teams отключена для пользователя.](media/remove-teams-licenses-1.png)    | ![Снимок экрана 2: лицензия Teams отключена для пользователя](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>С помощью PowerShell

Используйте PowerShell для управления лицензиями Teams для пользователей в массовом режиме. Вы включаете и отключаете Teams с помощью PowerShell так же, как и для любой другой лицензии плана обслуживания. Вам потребуются следующие идентификаторы для планов обслуживания Teams:

- Microsoft Teams: TEAMS1
- Microsoft Teams для GCC: TEAMS_GOV
- Microsoft Teams для DoD: TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>Массовое назначение лицензий Teams

Подробные инструкции см. в статье [Назначение лицензий учетным записям пользователей с помощью PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="remove-teams-licenses-in-bulk"></a>Массовое удаление лицензий Teams

Подробные инструкции см. в [разделах Отключение доступа к службам с помощью PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) и [Отключение доступа к службам при назначении пользовательских лицензий](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).

#### <a name="example"></a>Пример 

Ниже приведен пример использования [командлетов New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) и [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) для отключения Teams для пользователей с определенным планом лицензирования. Например, выполните следующие действия, чтобы сначала отключить Teams для всех пользователей с определенным планом лицензирования. Затем включите Teams для каждого отдельного пользователя, который должен иметь доступ к Teams.

> [!IMPORTANT]
> Командлет [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) включает все службы, которые ранее были отключены, если они не определены явным образом в пользовательском скрипте. Например, если вы хотите оставить Exchange и Sway отключенными при отключении Teams, необходимо включить его в скрипт, иначе для указанных пользователей будут включены оба exchange и Sway.

Выполните следующую команду, чтобы отобразить все доступные планы лицензирования в организации. Дополнительные сведения см. в статье [Просмотр лицензий и служб с помощью PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).


```powershell
Get-MsolAccountSku
```

Выполните следующие команды, где \<CompanyName:License> — это название организации и идентификатор плана лицензирования, полученный на предыдущем шаге. Например, ContosoSchool:ENTERPRISEPACK_STUDENT.

```powershell
$acctSKU="<CompanyName:License>"
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

Выполните следующую команду, чтобы отключить Teams для всех пользователей, имеющих активную лицензию на план лицензирования.

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a>См. также

- [Лицензии на надстройки Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Назначение лицензий на надстройки Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [Просмотр лицензий и служб с помощью PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Названия продуктов и идентификаторы планов служб для лицензирования](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Справочник по SKU для образовательных учреждений](sku-reference-edu.md)
