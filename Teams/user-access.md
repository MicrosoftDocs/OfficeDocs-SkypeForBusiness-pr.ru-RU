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
# <a name="manage-user-access-to-teams"></a><span data-ttu-id="e6e6b-103">Управление доступом пользователей к Teams</span><span class="sxs-lookup"><span data-stu-id="e6e6b-103">Manage user access to Teams</span></span>

<span data-ttu-id="e6e6b-104">Управление доступом к Teams осуществляется на уровне пользователя с помощью назначения или удаления лицензии на продукт Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e6e6b-104">You manage access to Teams at the user level by assigning or removing a Microsoft Teams product license.</span></span> <span data-ttu-id="e6e6b-105">У каждого пользователя в вашей организации должна быть лицензия Teams, прежде чем они смогут использовать Teams.</span><span class="sxs-lookup"><span data-stu-id="e6e6b-105">Each user in your organization must have a Teams license before they can use Teams.</span></span> <span data-ttu-id="e6e6b-106">Вы можете назначить лицензию Teams для новых пользователей при создании новых учетных записей пользователей или для пользователей с существующими учетными записями.</span><span class="sxs-lookup"><span data-stu-id="e6e6b-106">You can assign a Teams license for new users when new user accounts are created or to users with existing accounts.</span></span>

<span data-ttu-id="e6e6b-107">По умолчанию, когда пользователю назначается план лицензирования (например, Microsoft 365 корпоративный E3 или Microsoft 365 Business Premium), ему автоматически назначается лицензия Teams, и пользователь включает команды.</span><span class="sxs-lookup"><span data-stu-id="e6e6b-107">By default, when a licensing plan (for example, Microsoft 365 Enterprise E3 or Microsoft 365 Business Premium)  is assigned to a user, a Teams license is automatically assigned, and the user is enabled for Teams.</span></span> <span data-ttu-id="e6e6b-108">Вы можете отключить или включить команды для пользователя, удалив или назначив лицензию в любое время.</span><span class="sxs-lookup"><span data-stu-id="e6e6b-108">You can disable or enable Teams for a user by removing or assigning a license at any time.</span></span>

<span data-ttu-id="e6e6b-109">Вы управляете лицензиями Teams в центре администрирования Microsoft 365 или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6e6b-109">You manage Teams licenses in the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="e6e6b-110">Для управления лицензиями необходимо быть глобальным администратором или администратором управления пользователями.</span><span class="sxs-lookup"><span data-stu-id="e6e6b-110">You must be a Global admin or User management admin to manage licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="e6e6b-111">Рекомендуется включить команды для всех пользователей, чтобы обеспечить согласованное формирование групп для проектов и других динамических инициатив.</span><span class="sxs-lookup"><span data-stu-id="e6e6b-111">We recommend that you enable Teams for all users so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="e6e6b-112">Даже если вы используете пилотный проект, он может быть полезен для поддержки групп для всех пользователей, но только для тех целей, которые предназначены только для пилотной группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="e6e6b-112">Even if you're running a pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="e6e6b-113">Использование центра администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e6e6b-113">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="e6e6b-114">С помощью центра администрирования Microsoft 365 вы можете управлять лицензиями Teams для отдельных пользователей и небольшим количество пользователей за один раз.</span><span class="sxs-lookup"><span data-stu-id="e6e6b-114">Use the Microsoft 365 admin center to manage Teams licenses for individual users or small sets of users at a time.</span></span> <span data-ttu-id="e6e6b-115">Вы можете управлять лицензиями Teams на странице **лицензий** (для более 20 пользователей в данный момент) или страницы " **Активные пользователи** ".</span><span class="sxs-lookup"><span data-stu-id="e6e6b-115">You can manage Teams licenses on the **Licenses** page (for up to 20 users at at time) or **Active users** page.</span></span> <span data-ttu-id="e6e6b-116">Выбор метода зависит от того, хотите ли вы управлять лицензиями на продукты для конкретных пользователей или управлять лицензиями пользователей для конкретных продуктов.</span><span class="sxs-lookup"><span data-stu-id="e6e6b-116">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="e6e6b-117">Если вам нужно управлять лицензиями Teams для большого количества пользователей, например сотни или тысячи пользователей, [используйте PowerShell](#using-powershell) или [Лицензирование на основе групп в Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="e6e6b-117">If you need to manage Teams licenses for a large number of users, such as hundreds or thousands of users, [use Powershell](#using-powershell) or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span> 

### <a name="assign-a-teams-license"></a><span data-ttu-id="e6e6b-118">Назначение лицензии Teams</span><span class="sxs-lookup"><span data-stu-id="e6e6b-118">Assign a Teams license</span></span>

<span data-ttu-id="e6e6b-119">Эти действия различаются в зависимости от того, используете ли вы страницу " **лицензии** " или " **Активные пользователи** ".</span><span class="sxs-lookup"><span data-stu-id="e6e6b-119">The steps are different depending on whether you use the **Licenses** page or **Active users** page.</span></span>  <span data-ttu-id="e6e6b-120">Пошаговые инструкции приведены [в статье Назначение лицензий пользователям](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="e6e6b-120">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

|||
|---------|---------|
|![Снимок экрана: лицензия на Teams включена для пользователя](media/assign-teams-licenses-1.png)    | ![Снимок экрана: лицензия на Teams включена для пользователя](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a><span data-ttu-id="e6e6b-123">Удаление лицензии Teams</span><span class="sxs-lookup"><span data-stu-id="e6e6b-123">Remove a Teams license</span></span>

<span data-ttu-id="e6e6b-124">При удалении лицензии на Teams от пользователя группы отключаются для этого пользователя, и они больше не будут отображаться в средстве запуска приложений или на домашней странице.</span><span class="sxs-lookup"><span data-stu-id="e6e6b-124">When you remove a Teams license from a user, Teams is disabled for that user, and they will no longer see Teams in the app launcher or homepage.</span></span> <span data-ttu-id="e6e6b-125">Подробные инструкции можно найти [в разделе Отмена назначения лицензий пользователям](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users).</span><span class="sxs-lookup"><span data-stu-id="e6e6b-125">For detailed steps, see [Unassign licenses from users](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users).</span></span>

|||
|---------|---------|
|![Снимок экрана: лицензия Teams отключена для пользователя](media/remove-teams-licenses-1.png)    | ![Снимок экрана: лицензия Teams отключена для пользователя](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a><span data-ttu-id="e6e6b-128">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6e6b-128">Using PowerShell</span></span>

<span data-ttu-id="e6e6b-129">Использование PowerShell для управления лицензиями Teams для пользователей в пакетном режиме.</span><span class="sxs-lookup"><span data-stu-id="e6e6b-129">Use PowerShell to manage Teams licenses for users in bulk.</span></span> <span data-ttu-id="e6e6b-130">Вы можете включать и отключать команды с помощью PowerShell так же, как и для других лицензий на план обслуживания.</span><span class="sxs-lookup"><span data-stu-id="e6e6b-130">You enable and disable Teams through PowerShell in the same way that you would for any other service plan license.</span></span> <span data-ttu-id="e6e6b-131">Для планов обслуживания для Teams вам понадобятся идентификаторы, указанные ниже.</span><span class="sxs-lookup"><span data-stu-id="e6e6b-131">You'll need the identifiers for the service plans for Teams, which are as follows:</span></span>

- <span data-ttu-id="e6e6b-132">Microsoft teams: TEAMS1</span><span class="sxs-lookup"><span data-stu-id="e6e6b-132">Microsoft Teams: TEAMS1</span></span>
- <span data-ttu-id="e6e6b-133">Microsoft Teams для GCC: TEAMS_GOV</span><span class="sxs-lookup"><span data-stu-id="e6e6b-133">Microsoft Teams for GCC: TEAMS_GOV</span></span>
- <span data-ttu-id="e6e6b-134">Microsoft Teams для вызова по требованию: TEAMS_DOD</span><span class="sxs-lookup"><span data-stu-id="e6e6b-134">Microsoft Teams for DoD: TEAMS_DOD</span></span>

### <a name="assign-teams-licenses-in-bulk"></a><span data-ttu-id="e6e6b-135">Массовое Назначение лицензий Teams</span><span class="sxs-lookup"><span data-stu-id="e6e6b-135">Assign Teams licenses in bulk</span></span>

<span data-ttu-id="e6e6b-136">Подробное описание действий можно найти [в статье Назначение лицензий для учетных записей пользователей с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="e6e6b-136">For detailed steps, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="remove-teams-licenses-in-bulk"></a><span data-ttu-id="e6e6b-137">Массовое удаление лицензий Teams</span><span class="sxs-lookup"><span data-stu-id="e6e6b-137">Remove Teams licenses in bulk</span></span>

<span data-ttu-id="e6e6b-138">Подробные инструкции можно найти в статье [Отключение доступа к службам с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) и [Отключение доступа к службам при назначении лицензий пользователей](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span><span class="sxs-lookup"><span data-stu-id="e6e6b-138">For detailed steps, see [Disable access to services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and [Disable access to services while assigning user licenses](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span></span>

#### <a name="example"></a><span data-ttu-id="e6e6b-139">Пример</span><span class="sxs-lookup"><span data-stu-id="e6e6b-139">Example</span></span> 

<span data-ttu-id="e6e6b-140">В следующем примере показано, как использовать командлеты [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) и [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) для отключения групп для пользователей с определенным планом лицензирования.</span><span class="sxs-lookup"><span data-stu-id="e6e6b-140">The following is an example of how to use the [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) and [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) cmdlets to disable Teams for users who have a specific licensing plan.</span></span> <span data-ttu-id="e6e6b-141">Например, чтобы сначала отключить группы для всех пользователей, имеющих определенный план лицензирования, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e6e6b-141">For example, follow these steps to first disable Teams for all users who have a particular licensing plan.</span></span> <span data-ttu-id="e6e6b-142">Затем включите команды для каждого отдельного пользователя, который должен иметь доступ к Teams.</span><span class="sxs-lookup"><span data-stu-id="e6e6b-142">Then enable Teams for each individual user who should have access to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6e6b-143">Командлет [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) включит все службы, которые ранее были отключены, если они не были явно идентифицированы в настраиваемом сценарии.</span><span class="sxs-lookup"><span data-stu-id="e6e6b-143">The [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) cmdlet will enable all services that were previously disabled unless explicitly identified in your custom script.</span></span> <span data-ttu-id="e6e6b-144">Например, если вы хотите отключать как Exchange, так и Sway при отключении групп, вам потребуется включить эту функцию в сценарий или оба сервера Exchange и Sway будут включены для указанных вами пользователей.</span><span class="sxs-lookup"><span data-stu-id="e6e6b-144">For example, if you want to leave both Exchange and Sway disabled while also disabling Teams, you'll need to include this in the script or both Exchange and Sway will be enabled for those users you identified.</span></span>

<span data-ttu-id="e6e6b-145">Чтобы отобразить все доступные планы лицензирования в вашей организации, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e6e6b-145">Run the following command to display all available licensing plans in your organization.</span></span> <span data-ttu-id="e6e6b-146">Дополнительные сведения можно найти в статье [Просмотр лицензий и служб с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="e6e6b-146">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span></span>

      Get-MsolAccountSku

<span data-ttu-id="e6e6b-147">Выполните указанные ниже команды, где \<CompanyName: License> — название вашей организации и идентификатор плана лицензирования, полученный на предыдущем этапе.</span><span class="sxs-lookup"><span data-stu-id="e6e6b-147">Run the following commands, where \<CompanyName:License> is your organization name and the identifier for the licensing plan that you retrieved in the earlier step.</span></span> <span data-ttu-id="e6e6b-148">Например, ContosoSchool: ENTERPRISEPACK_STUDENT.</span><span class="sxs-lookup"><span data-stu-id="e6e6b-148">For example, ContosoSchool:ENTERPRISEPACK_STUDENT.</span></span>

      $acctSKU="<CompanyName:License>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"

<span data-ttu-id="e6e6b-149">Чтобы отключить команды для всех пользователей, у которых есть действующая лицензия на план лицензирования, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e6e6b-149">Run the following command to disable Teams for all users who have an active license for the licensing plan.</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

## <a name="manage-teams-at-the-organization-level"></a><span data-ttu-id="e6e6b-150">Управление группами на уровне Организации</span><span class="sxs-lookup"><span data-stu-id="e6e6b-150">Manage teams at the organization level</span></span>

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

## <a name="related-topics"></a><span data-ttu-id="e6e6b-151">См. также</span><span class="sxs-lookup"><span data-stu-id="e6e6b-151">Related topics</span></span>

- [<span data-ttu-id="e6e6b-152">Лицензии на надстройки Teams</span><span class="sxs-lookup"><span data-stu-id="e6e6b-152">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="e6e6b-153">Назначение лицензий на надстройки Teams</span><span class="sxs-lookup"><span data-stu-id="e6e6b-153">Assign Teams add-on licenses</span></span>](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [<span data-ttu-id="e6e6b-154">Просмотр лицензий и служб с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6e6b-154">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="e6e6b-155">Названия продуктов и идентификаторы планов служб для лицензирования</span><span class="sxs-lookup"><span data-stu-id="e6e6b-155">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="e6e6b-156">Справочник по образовательной конфигурации</span><span class="sxs-lookup"><span data-stu-id="e6e6b-156">Education SKU reference</span></span>](sku-reference-edu.md)