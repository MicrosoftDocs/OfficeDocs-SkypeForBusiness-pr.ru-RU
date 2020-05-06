---
title: Управление доступом пользователей к Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.reviewer: ritikag
search.appverid: MET150
description: Сведения о том, как управлять доступом пользователей к Teams с помощью назначения и удаления лицензий на группы для пользователей в вашей организации.
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32ab8f68ef1c37fbb5cb724b322b4db0ee757b84
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042276"
---
# <a name="manage-user-access-to-teams"></a>Управление доступом пользователей к Teams

Управление доступом к Teams осуществляется на уровне пользователя с помощью назначения или удаления лицензии на продукт Microsoft Teams. У каждого пользователя в вашей организации должна быть лицензия Teams, прежде чем они смогут использовать Teams. Вы можете назначить лицензию Teams для новых пользователей при создании новых учетных записей пользователей или для пользователей с существующими учетными записями.

По умолчанию, когда пользователю назначается план лицензирования (например, Microsoft 365 корпоративный E3 или Microsoft 365 Business Premium), ему автоматически назначается лицензия Teams, и пользователь включает команды. Вы можете отключить или включить команды для пользователя, удалив или назначив лицензию в любое время.

Вы управляете лицензиями Teams в центре администрирования Microsoft 365 или с помощью PowerShell. Для управления лицензиями необходимо быть глобальным администратором или администратором управления пользователями.

> [!NOTE]
> Рекомендуется включить команды для всех пользователей, чтобы обеспечить согласованное формирование групп для проектов и других динамических инициатив. Даже если вы используете пилотный проект, он может быть полезен для поддержки групп для всех пользователей, но только для тех целей, которые предназначены только для пилотной группы пользователей.

## <a name="using-the-microsoft-365-admin-center"></a>Использование центра администрирования Microsoft 365

С помощью центра администрирования Microsoft 365 вы можете управлять лицензиями Teams для отдельных пользователей и небольшим количество пользователей за один раз. Вы можете управлять лицензиями Teams на странице **лицензий** (для более 20 пользователей в данный момент) или страницы " **Активные пользователи** ". Выбор метода зависит от того, хотите ли вы управлять лицензиями на продукты для конкретных пользователей или управлять лицензиями пользователей для конкретных продуктов.

Если вам нужно управлять лицензиями Teams для большого количества пользователей, например сотни или тысячи пользователей, [используйте PowerShell](#using-powershell) или [Лицензирование на основе групп в Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign). 

### <a name="assign-a-teams-license"></a>Назначение лицензии Teams

Эти действия различаются в зависимости от того, используете ли вы страницу " **лицензии** " или " **Активные пользователи** ".  Пошаговые инструкции приведены [в статье Назначение лицензий пользователям](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

|||
|---------|---------|
|![Снимок экрана: лицензия на Teams включена для пользователя](media/assign-teams-licenses-1.png)    | ![Снимок экрана: лицензия на Teams включена для пользователя](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>Удаление лицензии Teams

При удалении лицензии на Teams от пользователя группы отключаются для этого пользователя, и они больше не будут отображаться в средстве запуска приложений или на домашней странице. Подробные инструкции можно найти [в разделе Отмена назначения лицензий пользователям](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users).

|||
|---------|---------|
|![Снимок экрана: лицензия Teams отключена для пользователя](media/remove-teams-licenses-1.png)    | ![Снимок экрана: лицензия Teams отключена для пользователя](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>Использование PowerShell

Использование PowerShell для управления лицензиями Teams для пользователей в пакетном режиме. Вы можете включать и отключать команды с помощью PowerShell так же, как и для других лицензий на план обслуживания. Для планов обслуживания для Teams вам понадобятся идентификаторы, указанные ниже.

- Microsoft teams: TEAMS1
- Microsoft Teams для GCC: TEAMS_GOV
- Microsoft Teams для вызова по требованию: TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>Массовое Назначение лицензий Teams

Подробное описание действий можно найти [в статье Назначение лицензий для учетных записей пользователей с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="remove-teams-licenses-in-bulk"></a>Массовое удаление лицензий Teams

Подробные инструкции можно найти в статье [Отключение доступа к службам с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) и [Отключение доступа к службам при назначении лицензий пользователей](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).

#### <a name="example"></a>Пример 

В следующем примере показано, как использовать командлеты [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) и [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) для отключения групп для пользователей с определенным планом лицензирования. Например, чтобы сначала отключить группы для всех пользователей, имеющих определенный план лицензирования, выполните указанные ниже действия. Затем включите команды для каждого отдельного пользователя, который должен иметь доступ к Teams.

> [!IMPORTANT]
> Командлет [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) включит все службы, которые ранее были отключены, если они не были явно идентифицированы в настраиваемом сценарии. Например, если вы хотите отключать как Exchange, так и Sway при отключении групп, вам потребуется включить эту функцию в сценарий или оба сервера Exchange и Sway будут включены для указанных вами пользователей.

Чтобы отобразить все доступные планы лицензирования в вашей организации, выполните следующую команду: Дополнительные сведения можно найти в статье [Просмотр лицензий и служб с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).

      Get-MsolAccountSku

Выполните указанные ниже команды, где \<CompanyName: License> — название вашей организации и идентификатор плана лицензирования, полученный на предыдущем этапе. Например, ContosoSchool: ENTERPRISEPACK_STUDENT.

      $acctSKU="<CompanyName:License>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"

Чтобы отключить команды для всех пользователей, у которых есть действующая лицензия на план лицензирования, выполните следующую команду:

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

## <a name="manage-teams-at-the-organization-level"></a>Управление группами на уровне Организации

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

## <a name="related-topics"></a>См. также

- [Лицензии на надстройки Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Назначение лицензий на надстройки Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [Просмотр лицензий и служб с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Названия продуктов и идентификаторы планов служб для лицензирования](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Справочник по образовательной конфигурации](sku-reference-edu.md)