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
ms.openlocfilehash: 29cf3f6816b3c1e0b00026b1ba4ad961a6a92aa6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093543"
---
# <a name="manage-user-access-to-teams"></a><span data-ttu-id="8203a-103">Управление доступом пользователей к Teams</span><span class="sxs-lookup"><span data-stu-id="8203a-103">Manage user access to Teams</span></span>

<span data-ttu-id="8203a-104">Вы управляете доступом к Teams на уровне пользователя, назначая или удаляя лицензию продукта Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8203a-104">You manage access to Teams at the user level by assigning or removing a Microsoft Teams product license.</span></span> <span data-ttu-id="8203a-105">За исключением анонимного присоединения к собраниям Teams, у каждого пользователя в организации должна быть лицензия на Teams, чтобы он мог использовать Teams.</span><span class="sxs-lookup"><span data-stu-id="8203a-105">Except for joining Teams meetings anonymously, each user in your organization must have a Teams license before they can use Teams.</span></span> <span data-ttu-id="8203a-106">Вы можете назначать лицензии Teams новым пользователям при их созданных учетных записях или пользователям с уже существующими учетными записьми.</span><span class="sxs-lookup"><span data-stu-id="8203a-106">You can assign a Teams license for new users when new user accounts are created or to users with existing accounts.</span></span>

<span data-ttu-id="8203a-107">По умолчанию при назначении пользователю плана лицензирования (например, Microsoft 365 корпоративный E3 или Microsoft 365 бизнес премиум) ему автоматически назначена лицензия Teams, а для пользователя включена возможность работы с Teams.</span><span class="sxs-lookup"><span data-stu-id="8203a-107">By default, when a licensing plan (for example, Microsoft 365 Enterprise E3 or Microsoft 365 Business Premium) is assigned to a user, a Teams license is automatically assigned, and the user is enabled for Teams.</span></span> <span data-ttu-id="8203a-108">Вы можете в любое время отключить или включить Teams для пользователя, удалив или назначив лицензию.</span><span class="sxs-lookup"><span data-stu-id="8203a-108">You can disable or enable Teams for a user by removing or assigning a license at any time.</span></span>

<span data-ttu-id="8203a-109">Используйте политики обмена сообщениями, управляемые в Центре администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams,</a>чтобы управлять тем, какие функции чата и каналов доступны пользователям в Teams.</span><span class="sxs-lookup"><span data-stu-id="8203a-109">Use messaging policies, managed from the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams Admin Center</a>, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="8203a-110">Вы можете использовать политику по умолчанию или создать одну или несколько настраиваемой политики обмена сообщениями для пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="8203a-110">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="8203a-111">Подробнее об этом можно узнать в [документе "Управление политиками обмена сообщениями в Teams".](messaging-policies-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="8203a-111">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>
<span data-ttu-id="8203a-112">Вы управляете лицензиями Teams в Центре администрирования Microsoft 365 или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8203a-112">You manage Teams licenses in the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="8203a-113">Для управления лицензиями необходимо быть глобальным администратором или администратором управления пользователями.</span><span class="sxs-lookup"><span data-stu-id="8203a-113">You must be a Global admin or User management admin to manage licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="8203a-114">Мы рекомендуем включить Teams для всех пользователей, чтобы команды могли быть сформированы для проектов и других динамических инициатив.</span><span class="sxs-lookup"><span data-stu-id="8203a-114">We recommend that you enable Teams for all users so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="8203a-115">Даже если вы работаете в пилотном проекте, может быть полезно поддерживать Teams включенным для всех пользователей, но поддерживать целевое взаимодействие только с пилотной группой пользователей.</span><span class="sxs-lookup"><span data-stu-id="8203a-115">Even if you're running a pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="8203a-116">Использование Центра администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8203a-116">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="8203a-117">Управление лицензиями на уровне пользователей Teams напрямую через интерфейсы управления пользователями в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8203a-117">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="8203a-118">Администратор может назначать лицензии для новых пользователей при создании их учетных записей, а также для пользователей с существующими учетными записями.</span><span class="sxs-lookup"><span data-stu-id="8203a-118">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="8203a-119">Администратор должен иметь права глобального администратора или администратора управления пользователями для управления лицензиями Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8203a-119">The administrator must have Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>
<span data-ttu-id="8203a-120">С помощью Центра администрирования Microsoft 365 можно управлять лицензиями Teams для отдельных пользователей или небольших наборов пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="8203a-120">Use the Microsoft 365 admin center to manage Teams licenses for individual users or small sets of users at a time.</span></span> <span data-ttu-id="8203a-121">Вы можете управлять лицензиями Teams на странице **"Лицензии"** (одновременно до 20 пользователей) или на странице **"Активные пользователи".**</span><span class="sxs-lookup"><span data-stu-id="8203a-121">You can manage Teams licenses on the **Licenses** page (for up to 20 users at at time) or **Active users** page.</span></span> <span data-ttu-id="8203a-122">Выбор метода зависит от того, хотите ли вы управлять лицензиями на продукты для определенных пользователей или лицензиями пользователей для определенных продуктов.</span><span class="sxs-lookup"><span data-stu-id="8203a-122">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="8203a-123">Если вам нужно управлять лицензиями Teams для большого количества пользователей, например сотен или тысяч пользователей, используйте [PowerShell](#using-powershell) или групповое лицензирование в [Azure Active Directory (Azure AD).](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="8203a-123">If you need to manage Teams licenses for a large number of users, such as hundreds or thousands of users, [use PowerShell](#using-powershell) or [group-based licensing in Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span> 

### <a name="assign-a-teams-license"></a><span data-ttu-id="8203a-124">Назначение лицензии Teams</span><span class="sxs-lookup"><span data-stu-id="8203a-124">Assign a Teams license</span></span>

<span data-ttu-id="8203a-125">Действия зависят от того, используете ли вы страницу **"Лицензии"** или **"Активные пользователи".**</span><span class="sxs-lookup"><span data-stu-id="8203a-125">The steps are different depending on whether you use the **Licenses** page or **Active users** page.</span></span>  <span data-ttu-id="8203a-126">Пошаговую инструкцию см. в инструкции по [назначению лицензий пользователям.](/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="8203a-126">For step-by-step instructions, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

|||
|---------|---------|
|![Снимок экрана: лицензия Teams включена для пользователя](media/assign-teams-licenses-1.png)    | ![Снимок экрана: лицензия Teams включена для пользователя](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a><span data-ttu-id="8203a-129">Удаление лицензии Teams</span><span class="sxs-lookup"><span data-stu-id="8203a-129">Remove a Teams license</span></span>

<span data-ttu-id="8203a-130">Когда вы удаляете лицензию Teams у пользователя, Teams отключается для этого пользователя и он больше не будет видеть Teams в приложении для запуска приложений или на домашней странице.</span><span class="sxs-lookup"><span data-stu-id="8203a-130">When you remove a Teams license from a user, Teams is disabled for that user, and they will no longer see Teams in the app launcher or homepage.</span></span> <span data-ttu-id="8203a-131">Подробные инструкции см. в описании отзыва [лицензий у пользователей.](/microsoft-365/admin/manage/remove-licenses-from-users)</span><span class="sxs-lookup"><span data-stu-id="8203a-131">For detailed steps, see [Unassign licenses from users](/microsoft-365/admin/manage/remove-licenses-from-users).</span></span>

|||
|---------|---------|
|![Снимок экрана: отключенная лицензия Teams для пользователя](media/remove-teams-licenses-1.png)    | ![Снимок экрана: отключенная лицензия Teams для пользователя](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a><span data-ttu-id="8203a-134">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="8203a-134">Using PowerShell</span></span>

<span data-ttu-id="8203a-135">Используйте PowerShell для массового управления лицензиями Teams для пользователей.</span><span class="sxs-lookup"><span data-stu-id="8203a-135">Use PowerShell to manage Teams licenses for users in bulk.</span></span> <span data-ttu-id="8203a-136">Команды можно включить и отключить с помощью PowerShell так же, как и для любой другой лицензии на план обслуживания.</span><span class="sxs-lookup"><span data-stu-id="8203a-136">You enable and disable Teams through PowerShell in the same way that you would for any other service plan license.</span></span> <span data-ttu-id="8203a-137">Вам нужны идентификаторы планов обслуживания для Teams:</span><span class="sxs-lookup"><span data-stu-id="8203a-137">You'll need the identifiers for the service plans for Teams, which are as follows:</span></span>

- <span data-ttu-id="8203a-138">Microsoft Teams: TEAMS1</span><span class="sxs-lookup"><span data-stu-id="8203a-138">Microsoft Teams: TEAMS1</span></span>
- <span data-ttu-id="8203a-139">Microsoft Teams для GCC: TEAMS_GOV</span><span class="sxs-lookup"><span data-stu-id="8203a-139">Microsoft Teams for GCC: TEAMS_GOV</span></span>
- <span data-ttu-id="8203a-140">Microsoft Teams для DoD: TEAMS_DOD</span><span class="sxs-lookup"><span data-stu-id="8203a-140">Microsoft Teams for DoD: TEAMS_DOD</span></span>

### <a name="assign-teams-licenses-in-bulk"></a><span data-ttu-id="8203a-141">Массовое назначение лицензий Teams</span><span class="sxs-lookup"><span data-stu-id="8203a-141">Assign Teams licenses in bulk</span></span>

<span data-ttu-id="8203a-142">Подробные инструкции см. в описании назначения лицензий учетным [записям пользователей с помощью PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="8203a-142">For detailed steps, see [Assign licenses to user accounts with PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="remove-teams-licenses-in-bulk"></a><span data-ttu-id="8203a-143">Массовое удаление лицензий Teams</span><span class="sxs-lookup"><span data-stu-id="8203a-143">Remove Teams licenses in bulk</span></span>

<span data-ttu-id="8203a-144">Подробные инструкции см. в описании отключения доступа к службам с помощью [PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) и отключения доступа к службам при назначении [пользовательских лицензий.](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)</span><span class="sxs-lookup"><span data-stu-id="8203a-144">For detailed steps, see [Disable access to services with PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and [Disable access to services while assigning user licenses](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span></span>

#### <a name="example"></a><span data-ttu-id="8203a-145">Пример</span><span class="sxs-lookup"><span data-stu-id="8203a-145">Example</span></span> 

<span data-ttu-id="8203a-146">Ниже приводится пример использования командлетов [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) и [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) для отключения Teams для пользователей с определенным планом лицензирования.</span><span class="sxs-lookup"><span data-stu-id="8203a-146">The following is an example of how to use the [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) and [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) cmdlets to disable Teams for users who have a specific licensing plan.</span></span> <span data-ttu-id="8203a-147">Например, выполните эти действия, чтобы сначала отключить Teams для всех пользователей с определенным планом лицензирования.</span><span class="sxs-lookup"><span data-stu-id="8203a-147">For example, follow these steps to first disable Teams for all users who have a particular licensing plan.</span></span> <span data-ttu-id="8203a-148">Затем в течение этого действия в teams можно включить Teams для каждого отдельного пользователя, которому должен быть доступ к Teams.</span><span class="sxs-lookup"><span data-stu-id="8203a-148">Then enable Teams for each individual user who should have access to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8203a-149">С [помощью cmdlet New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) можно включить все службы, которые ранее были отключены, если они не были явно определены в настраиваемом сценарии.</span><span class="sxs-lookup"><span data-stu-id="8203a-149">The [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) cmdlet will enable all services that were previously disabled unless explicitly identified in your custom script.</span></span> <span data-ttu-id="8203a-150">Например, если вы хотите оставить отключенными и Exchange, и Sway, а также отключить Teams, вам потребуется включить это в сценарий или для этих пользователей будут включены Exchange и Sway.</span><span class="sxs-lookup"><span data-stu-id="8203a-150">For example, if you want to leave both Exchange and Sway disabled while also disabling Teams, you'll need to include this in the script or both Exchange and Sway will be enabled for those users you identified.</span></span>

<span data-ttu-id="8203a-151">Чтобы отобразить все доступные планы лицензирования в вашей организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8203a-151">Run the following command to display all available licensing plans in your organization.</span></span> <span data-ttu-id="8203a-152">Подробнее см. в [лицензиях и службах PowerShell.](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="8203a-152">To learn more, see [View licenses and services with PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span></span>


```powershell
Get-MsolAccountSku
```

<span data-ttu-id="8203a-153">Запустите следующие команды: название организации и идентификатор плана лицензирования, который вы извлекли на \<CompanyName:License> предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="8203a-153">Run the following commands, where \<CompanyName:License> is your organization name and the identifier for the licensing plan that you retrieved in the earlier step.</span></span> <span data-ttu-id="8203a-154">Например, ContosoSchool:ENTERPRISEPACK_STUDENT.</span><span class="sxs-lookup"><span data-stu-id="8203a-154">For example, ContosoSchool:ENTERPRISEPACK_STUDENT.</span></span>

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

<span data-ttu-id="8203a-155">Чтобы отключить Teams для всех пользователей с действующей лицензией для плана лицензирования, следуя следующей команде:</span><span class="sxs-lookup"><span data-stu-id="8203a-155">Run the following command to disable Teams for all users who have an active license for the licensing plan.</span></span>

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a><span data-ttu-id="8203a-156">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8203a-156">Related topics</span></span>

- [<span data-ttu-id="8203a-157">Лицензии на надстройки Teams</span><span class="sxs-lookup"><span data-stu-id="8203a-157">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="8203a-158">Назначение лицензий на надстройки Teams</span><span class="sxs-lookup"><span data-stu-id="8203a-158">Assign Teams add-on licenses</span></span>](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [<span data-ttu-id="8203a-159">Просмотр лицензий и служб с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="8203a-159">View licenses and services with PowerShell</span></span>](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="8203a-160">Названия продуктов и идентификаторы планов служб для лицензирования</span><span class="sxs-lookup"><span data-stu-id="8203a-160">Product names and service plan identifiers for licensing</span></span>](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="8203a-161">Справка по SKU для образования</span><span class="sxs-lookup"><span data-stu-id="8203a-161">Education SKU reference</span></span>](sku-reference-edu.md)