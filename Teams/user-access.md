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
ms.openlocfilehash: 770dcea62d6f3dc65f576a3d64a520dd4de2ecad
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637731"
---
# <a name="manage-user-access-to-teams"></a><span data-ttu-id="35c9a-103">Управление доступом пользователей к Teams</span><span class="sxs-lookup"><span data-stu-id="35c9a-103">Manage user access to Teams</span></span>

<span data-ttu-id="35c9a-104">Вы управляете доступом Teams пользователями, назначая или удаляя лицензии Microsoft Teams продуктов.</span><span class="sxs-lookup"><span data-stu-id="35c9a-104">You manage access to Teams at the user level by assigning or removing a Microsoft Teams product license.</span></span> <span data-ttu-id="35c9a-105">За исключением Teams анонимного присоединения к собраниям, у каждого пользователя в организации должна быть Teams лицензия, прежде чем он сможет Teams.</span><span class="sxs-lookup"><span data-stu-id="35c9a-105">Except for joining Teams meetings anonymously, each user in your organization must have a Teams license before they can use Teams.</span></span> <span data-ttu-id="35c9a-106">Вы можете назначить лицензию Teams пользователям при их создания или пользователям с существующими учетными данными.</span><span class="sxs-lookup"><span data-stu-id="35c9a-106">You can assign a Teams license for new users when new user accounts are created or to users with existing accounts.</span></span>

<span data-ttu-id="35c9a-107">По умолчанию, когда пользователю назначен план лицензирования (например, Microsoft 365 корпоративный E3 или Microsoft 365 бизнес премиум), ему автоматически назначена лицензия Teams, а пользователю включена Teams.</span><span class="sxs-lookup"><span data-stu-id="35c9a-107">By default, when a licensing plan (for example, Microsoft 365 Enterprise E3 or Microsoft 365 Business Premium) is assigned to a user, a Teams license is automatically assigned, and the user is enabled for Teams.</span></span> <span data-ttu-id="35c9a-108">Вы можете отключить или включить Teams для пользователя, удалив или назначив лицензию в любое время.</span><span class="sxs-lookup"><span data-stu-id="35c9a-108">You can disable or enable Teams for a user by removing or assigning a license at any time.</span></span>

<span data-ttu-id="35c9a-109">Используйте политики обмена сообщениями, управляемые в Центре администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams</a>, чтобы управлять тем, какие функции чата и сообщений каналов доступны пользователям в Teams.</span><span class="sxs-lookup"><span data-stu-id="35c9a-109">Use messaging policies, managed from the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams Admin Center</a>, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="35c9a-110">Вы можете использовать политику по умолчанию или создать одну или несколько настраиваемой политики обмена сообщениями для пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="35c9a-110">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="35c9a-111">Дополнительные узнать об этом можно [в этой](messaging-policies-in-teams.md)Teams.</span><span class="sxs-lookup"><span data-stu-id="35c9a-111">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>
<span data-ttu-id="35c9a-112">Управление лицензиями Teams в центре администрирования Microsoft 365 с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="35c9a-112">You manage Teams licenses in the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="35c9a-113">Для управления лицензиями необходимо быть глобальным администратором или администратором управления пользователями.</span><span class="sxs-lookup"><span data-stu-id="35c9a-113">You must be a Global admin or User management admin to manage licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="35c9a-114">Мы рекомендуем включить Teams для всех пользователей, чтобы группы могли быть естественно сформированы для проектов и других динамических инициатив.</span><span class="sxs-lookup"><span data-stu-id="35c9a-114">We recommend that you enable Teams for all users so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="35c9a-115">Даже если вы работаете в пилотном проекте, может быть полезно включить Teams для всех пользователей, но только целевое взаимодействие с пилотной группой пользователей.</span><span class="sxs-lookup"><span data-stu-id="35c9a-115">Even if you're running a pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="35c9a-116">Использование центра Microsoft 365 администрирования</span><span class="sxs-lookup"><span data-stu-id="35c9a-116">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="35c9a-117">Teams лицензиями на уровне пользователя управляется непосредственно Microsoft 365 интерфейсов управления пользователями в Центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="35c9a-117">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="35c9a-118">Администратор может назначать лицензии для новых пользователей при создании их учетных записей, а также для пользователей с существующими учетными записями.</span><span class="sxs-lookup"><span data-stu-id="35c9a-118">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="35c9a-119">Администратор должен иметь права глобального администратора или администратора управления пользователями для управления Microsoft Teams лицензиями.</span><span class="sxs-lookup"><span data-stu-id="35c9a-119">The administrator must have Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>
<span data-ttu-id="35c9a-120">Центр администрирования Microsoft 365 для управления лицензиями Teams отдельными пользователями или небольшими наборами пользователей за раз.</span><span class="sxs-lookup"><span data-stu-id="35c9a-120">Use the Microsoft 365 admin center to manage Teams licenses for individual users or small sets of users at a time.</span></span> <span data-ttu-id="35c9a-121">Вы можете управлять Teams лицензиями  на странице Лицензии (одновременно до 20 пользователей) или На странице **Активные** пользователи.</span><span class="sxs-lookup"><span data-stu-id="35c9a-121">You can manage Teams licenses on the **Licenses** page (for up to 20 users at at time) or **Active users** page.</span></span> <span data-ttu-id="35c9a-122">Выбор метода зависит от того, хотите ли вы управлять лицензиями на продукты для определенных пользователей или лицензиями пользователей для определенных продуктов.</span><span class="sxs-lookup"><span data-stu-id="35c9a-122">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="35c9a-123">Если вам нужно управлять лицензиями Teams для большого количества пользователей, например сотен или тысяч пользователей, используйте [PowerShell](#using-powershell) или групповое лицензирование в Azure Active Directory [(Azure AD).](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="35c9a-123">If you need to manage Teams licenses for a large number of users, such as hundreds or thousands of users, [use PowerShell](#using-powershell) or [group-based licensing in Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span> 

### <a name="assign-a-teams-license"></a><span data-ttu-id="35c9a-124">Назначение лицензии Teams лицензии</span><span class="sxs-lookup"><span data-stu-id="35c9a-124">Assign a Teams license</span></span>

<span data-ttu-id="35c9a-125">Действия зависят от того, используете ли вы страницу **Лицензии** или **Активные** пользователи.</span><span class="sxs-lookup"><span data-stu-id="35c9a-125">The steps are different depending on whether you use the **Licenses** page or **Active users** page.</span></span>  <span data-ttu-id="35c9a-126">Пошаговую инструкцию см. в инструкциях по [назначению лицензий пользователям.](/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="35c9a-126">For step-by-step instructions, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

|||
|---------|---------|
|![Снимок экрана Teams лицензия включена для пользователя](media/assign-teams-licenses-1.png)    | ![Снимок экрана Teams лицензия включена для пользователя](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a><span data-ttu-id="35c9a-129">Удаление лицензии Teams лицензии</span><span class="sxs-lookup"><span data-stu-id="35c9a-129">Remove a Teams license</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35c9a-130">На отключение SKU Teams 24 часа.</span><span class="sxs-lookup"><span data-stu-id="35c9a-130">It takes about 24 hours for disabling a Teams SKU to take effect.</span></span>

<span data-ttu-id="35c9a-131">При Teams лицензии пользователя приложение Teams отключено, и он больше не будет Teams в приложении или на домашней странице.</span><span class="sxs-lookup"><span data-stu-id="35c9a-131">When you remove a Teams license from a user, Teams is disabled for that user, and they will no longer see Teams in the app launcher or homepage.</span></span> <span data-ttu-id="35c9a-132">Подробные инструкции см. в описании отзыва [лицензий у пользователей.](/microsoft-365/admin/manage/remove-licenses-from-users)</span><span class="sxs-lookup"><span data-stu-id="35c9a-132">For detailed steps, see [Unassign licenses from users](/microsoft-365/admin/manage/remove-licenses-from-users).</span></span>

|||
|---------|---------|
|![Снимок экрана Teams отключенной лицензии для пользователя](media/remove-teams-licenses-1.png)    | ![Снимок экрана Teams отключенной лицензии для пользователя](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a><span data-ttu-id="35c9a-135">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="35c9a-135">Using PowerShell</span></span>

<span data-ttu-id="35c9a-136">Используйте PowerShell для массовой Teams лицензий для пользователей.</span><span class="sxs-lookup"><span data-stu-id="35c9a-136">Use PowerShell to manage Teams licenses for users in bulk.</span></span> <span data-ttu-id="35c9a-137">Вы включаете и отключая Teams PowerShell так же, как и для любой другой лицензии на план обслуживания.</span><span class="sxs-lookup"><span data-stu-id="35c9a-137">You enable and disable Teams through PowerShell in the same way that you would for any other service plan license.</span></span> <span data-ttu-id="35c9a-138">Вам нужны идентификаторы планов обслуживания для Teams:</span><span class="sxs-lookup"><span data-stu-id="35c9a-138">You'll need the identifiers for the service plans for Teams, which are as follows:</span></span>

- <span data-ttu-id="35c9a-139">Microsoft Teams: TEAMS1</span><span class="sxs-lookup"><span data-stu-id="35c9a-139">Microsoft Teams: TEAMS1</span></span>
- <span data-ttu-id="35c9a-140">Microsoft Teams для GCC: TEAMS_GOV</span><span class="sxs-lookup"><span data-stu-id="35c9a-140">Microsoft Teams for GCC: TEAMS_GOV</span></span>
- <span data-ttu-id="35c9a-141">Microsoft Teams для DoD: TEAMS_DOD</span><span class="sxs-lookup"><span data-stu-id="35c9a-141">Microsoft Teams for DoD: TEAMS_DOD</span></span>

### <a name="assign-teams-licenses-in-bulk"></a><span data-ttu-id="35c9a-142">Массовое Teams лицензий</span><span class="sxs-lookup"><span data-stu-id="35c9a-142">Assign Teams licenses in bulk</span></span>

<span data-ttu-id="35c9a-143">Подробные инструкции см. в описании назначения [лицензий учетным записям пользователей с помощью PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="35c9a-143">For detailed steps, see [Assign licenses to user accounts with PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="remove-teams-licenses-in-bulk"></a><span data-ttu-id="35c9a-144">Массовое Teams лицензий</span><span class="sxs-lookup"><span data-stu-id="35c9a-144">Remove Teams licenses in bulk</span></span>

<span data-ttu-id="35c9a-145">Подробные инструкции см. в инструкциях Отключение доступа к службам с помощью [PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) и Отключение доступа к службам при назначении [пользовательских лицензий.](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)</span><span class="sxs-lookup"><span data-stu-id="35c9a-145">For detailed steps, see [Disable access to services with PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and [Disable access to services while assigning user licenses](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span></span>

#### <a name="example"></a><span data-ttu-id="35c9a-146">Пример</span><span class="sxs-lookup"><span data-stu-id="35c9a-146">Example</span></span> 

<span data-ttu-id="35c9a-147">Ниже приводится пример использования [msolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) и [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) для отключения Teams для пользователей с определенным планом лицензирования.</span><span class="sxs-lookup"><span data-stu-id="35c9a-147">The following is an example of how to use the [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) and [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) cmdlets to disable Teams for users who have a specific licensing plan.</span></span> <span data-ttu-id="35c9a-148">Например, выполните эти действия, чтобы сначала отключить Teams для всех пользователей с определенным планом лицензирования.</span><span class="sxs-lookup"><span data-stu-id="35c9a-148">For example, follow these steps to first disable Teams for all users who have a particular licensing plan.</span></span> <span data-ttu-id="35c9a-149">Затем в Teams для каждого отдельного пользователя, которому должен быть доступ к Teams.</span><span class="sxs-lookup"><span data-stu-id="35c9a-149">Then enable Teams for each individual user who should have access to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35c9a-150">С [помощью msolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) можно включить все службы, которые ранее были отключены, если они не были явно определены в настраиваемом сценарии.</span><span class="sxs-lookup"><span data-stu-id="35c9a-150">The [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) cmdlet will enable all services that were previously disabled unless explicitly identified in your custom script.</span></span> <span data-ttu-id="35c9a-151">Например, если вы хотите одновременно отключить Exchange и Sway Teams, необходимо включить его в сценарий, иначе для этих пользователей будут включены Exchange и Sway.</span><span class="sxs-lookup"><span data-stu-id="35c9a-151">For example, if you want to leave both Exchange and Sway disabled while also disabling Teams, you'll need to include this in the script or both Exchange and Sway will be enabled for those users you identified.</span></span>

<span data-ttu-id="35c9a-152">Чтобы отобразить все доступные планы лицензирования в организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="35c9a-152">Run the following command to display all available licensing plans in your organization.</span></span> <span data-ttu-id="35c9a-153">Дополнительные действия см. в [этой](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)ссылке.</span><span class="sxs-lookup"><span data-stu-id="35c9a-153">To learn more, see [View licenses and services with PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span></span>


```powershell
Get-MsolAccountSku
```

<span data-ttu-id="35c9a-154">Для этого следуйте следующим командам: название организации и идентификатор плана лицензирования, который вы извлекли на более \<CompanyName:License> ранней этапе.</span><span class="sxs-lookup"><span data-stu-id="35c9a-154">Run the following commands, where \<CompanyName:License> is your organization name and the identifier for the licensing plan that you retrieved in the earlier step.</span></span> <span data-ttu-id="35c9a-155">Например, ContosoSchool:ENTERPRISEPACK_STUDENT.</span><span class="sxs-lookup"><span data-stu-id="35c9a-155">For example, ContosoSchool:ENTERPRISEPACK_STUDENT.</span></span>

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

<span data-ttu-id="35c9a-156">Чтобы отключить Teams для всех пользователей, у которых есть активная лицензия для плана лицензирования, следуя следующей команде:</span><span class="sxs-lookup"><span data-stu-id="35c9a-156">Run the following command to disable Teams for all users who have an active license for the licensing plan.</span></span>

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a><span data-ttu-id="35c9a-157">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="35c9a-157">Related topics</span></span>

- [<span data-ttu-id="35c9a-158">Teams надстройки</span><span class="sxs-lookup"><span data-stu-id="35c9a-158">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="35c9a-159">Назначение Teams надстройки</span><span class="sxs-lookup"><span data-stu-id="35c9a-159">Assign Teams add-on licenses</span></span>](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [<span data-ttu-id="35c9a-160">Просмотр лицензий и служб с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="35c9a-160">View licenses and services with PowerShell</span></span>](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="35c9a-161">Названия продуктов и идентификаторы планов служб для лицензирования</span><span class="sxs-lookup"><span data-stu-id="35c9a-161">Product names and service plan identifiers for licensing</span></span>](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="35c9a-162">Справка по SKU для образования</span><span class="sxs-lookup"><span data-stu-id="35c9a-162">Education SKU reference</span></span>](sku-reference-edu.md)
