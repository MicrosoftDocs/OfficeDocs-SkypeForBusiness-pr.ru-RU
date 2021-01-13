---
title: Управление доступом пользователей к Microsoft Teams
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: c4fdfddfe43fd977099a02df61bb74146afcb05d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804409"
---
# <a name="manage-user-access-to-teams"></a>Управление доступом пользователей к Teams

Вы управляете доступом к Teams на уровне пользователя, назначая или удаляя лицензию продукта Microsoft Teams. За исключением анонимного присоединения к собраниям Teams, у каждого пользователя в организации должна быть лицензия на Teams, чтобы он мог использовать Teams. Вы можете назначать лицензии Teams новым пользователям при их созданной учетной записи или пользователям с уже существующими учетными записьми.

По умолчанию при назначении пользователю плана лицензирования (например, Microsoft 365 корпоративный E3 или Microsoft 365 бизнес премиум) ему автоматически назначена лицензия Teams, а для пользователя включена возможность работы с Teams. Вы можете в любое время отключить или включить Teams для пользователя, удалив или назначив лицензию.

Используйте политики обмена сообщениями, управляемые в Центре администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams,</a>чтобы управлять тем, какие функции чата и каналов доступны пользователям в Teams. Вы можете использовать политику по умолчанию или создать одну или несколько настраиваемой политики обмена сообщениями для пользователей в организации. Подробнее об этом можно узнать в [документе "Управление политиками обмена сообщениями в Teams".](messaging-policies-in-teams.md)
Вы управляете лицензиями Teams в Центре администрирования Microsoft 365 или с помощью PowerShell. Для управления лицензиями необходимо быть глобальным администратором или администратором управления пользователями.

> [!NOTE]
> Мы рекомендуем включить Teams для всех пользователей, чтобы команды могли быть сформированы для проектов и других динамических инициатив. Даже если вы работаете в пилотном проекте, может быть полезно поддерживать Teams включенным для всех пользователей, но поддерживать целевое взаимодействие только с пилотной группой пользователей.

## <a name="using-the-microsoft-365-admin-center"></a>Использование Центра администрирования Microsoft 365

Управление лицензиями на уровне пользователей Teams напрямую через интерфейсы Управления пользователями в Центре администрирования Microsoft 365. Администратор может назначать лицензии для новых пользователей при создании их учетных записей, а также для пользователей с существующими учетными записями. 

> [!IMPORTANT]
> Администратор должен иметь права глобального администратора или администратора управления пользователями для управления лицензиями Microsoft Teams.
С помощью Центра администрирования Microsoft 365 можно управлять лицензиями Teams для отдельных пользователей или небольших наборов пользователей одновременно. Вы можете управлять лицензиями Teams на странице **"Лицензии"** (одновременно до 20 пользователей) или на странице **"Активные пользователи".** Выбор метода зависит от того, хотите ли вы управлять лицензиями на продукты для определенных пользователей или лицензиями пользователей для определенных продуктов.

Если вам нужно управлять лицензиями Teams для большого количества пользователей, например сотен или тысяч пользователей, используйте [PowerShell](#using-powershell) или групповое лицензирование в [Azure Active Directory (Azure AD).](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) 

### <a name="assign-a-teams-license"></a>Назначение лицензии Teams

Действия зависят от того, используете ли вы страницу **"Лицензии"** или **"Активные пользователи".**  Пошаговую инструкцию см. в инструкции по [назначению лицензий пользователям.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

|||
|---------|---------|
|![Снимок экрана: лицензия Teams включена для пользователя](media/assign-teams-licenses-1.png)    | ![Снимок экрана: лицензия Teams включена для пользователя](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>Удаление лицензии Teams

Когда вы удаляете лицензию Teams у пользователя, Teams отключается для этого пользователя и он больше не будет видеть Teams в приложении для запуска приложений или на домашней странице. Подробные инструкции см. в описании отзыва [лицензий у пользователей.](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users)

|||
|---------|---------|
|![Снимок экрана: отключенная лицензия Teams для пользователя](media/remove-teams-licenses-1.png)    | ![Снимок экрана: отключенная лицензия Teams для пользователя](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>С помощью PowerShell

Используйте PowerShell для массового управления лицензиями Teams для пользователей. Команды можно включить и отключить с помощью PowerShell так же, как и для любой другой лицензии на план обслуживания. Вам нужны идентификаторы планов обслуживания для Teams:

- Microsoft Teams: TEAMS1
- Microsoft Teams для GCC: TEAMS_GOV
- Microsoft Teams для DoD: TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>Массовое назначение лицензий Teams

Подробные инструкции см. в описании назначения лицензий учетным записям пользователей [с помощью PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)

### <a name="remove-teams-licenses-in-bulk"></a>Массовое удаление лицензий Teams

Подробные инструкции см. в описании отключения доступа к службам с помощью [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) и отключения доступа к службам при назначении [пользовательских лицензий.](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)

#### <a name="example"></a>Пример 

Ниже приводится пример использования командлетов [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) и [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) для отключения Teams для пользователей с определенным планом лицензирования. Например, выполните эти действия, чтобы сначала отключить Teams для всех пользователей с определенным планом лицензирования. Затем в течение этого действия в teams можно включить Teams для каждого отдельного пользователя, которому должен быть доступ к Teams.

> [!IMPORTANT]
> С [помощью cmdlet New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) можно включить все службы, которые ранее были отключены, если они не были явно определены в настраиваемом сценарии. Например, если вы хотите оставить отключенными и Exchange, и Sway, а также отключить Teams, вам потребуется включить это в сценарий либо для этих пользователей будут включены Exchange и Sway.

Чтобы отобразить все доступные планы лицензирования в вашей организации, запустите следующую команду: Подробнее см. в [лицензиях и службах PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)


```powershell
Get-MsolAccountSku
```

Запустите следующие команды: название организации и идентификатор для плана лицензирования, который вы извлечь на более \<CompanyName:License> ранней этапе. Например, ContosoSchool:ENTERPRISEPACK_STUDENT.

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

Чтобы отключить Teams для всех пользователей с действующей лицензией для плана лицензирования, следуя следующей команде:

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="manage-teams-at-the-organization-level"></a>Управление командами на уровне организации

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

## <a name="related-topics"></a>Статьи по теме

- [Лицензии на надстройки Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Назначение лицензий на надстройки Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [Просмотр лицензий и служб с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Названия продуктов и идентификаторы планов служб для лицензирования](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Справка по SKU для образования](sku-reference-edu.md)
