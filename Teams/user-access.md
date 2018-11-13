---
title: Управление доступом пользователей к Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: ritikag
search.appverid: MET150
description: Сведения о том, как включить или отключить доступ на уровне пользователей для отдельных лиц.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8336c3a8899e7719ae8ff50bb2bcdb9c6565c438
ms.sourcegitcommit: 8a6bf02958436fcdeed336f09079bd3827e2fccb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2018
ms.locfileid: "26282967"
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="adebe-103">Управление доступом пользователей к Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="adebe-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="adebe-104">На уровне пользователя доступ к группами Майкрософт могут включаться и отключаться на уровне пользователя с назначение или удаление лицензии группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="adebe-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="adebe-105">На данный момент нет способа политики для включения группы или подмножество функций группам включено или отключено на уровне отдельных пользователей за пределами лицензирования.</span><span class="sxs-lookup"><span data-stu-id="adebe-105">Currently, there are no policy options for turning Teams, or a subset of Teams features, on or off at an individual user level outside of licensing.</span></span>

> [!NOTE]
><span data-ttu-id="adebe-106">Корпорация Майкрософт рекомендует включить групп для всех пользователей в организации, чтобы команды может быть создана согласованным образом: для проектов и других динамических инициатив.</span><span class="sxs-lookup"><span data-stu-id="adebe-106">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="adebe-107">Даже в том случае, если принято решение о для пилотного, может быть полезно сохранить групп, включено для всех пользователей, но только предназначенных для коммуникаций для пилотной группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="adebe-107">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-teams-through-the-office-365-admin-center"></a><span data-ttu-id="adebe-108">Управление группами с помощью центра администрирования Office 365</span><span class="sxs-lookup"><span data-stu-id="adebe-108">Manage Teams through the Office 365 admin center</span></span>

<span data-ttu-id="adebe-109">Лицензий на уровне пользователей группам осуществляется непосредственно через Центр администрирования Office 365 пользовательских интерфейсов управления.</span><span class="sxs-lookup"><span data-stu-id="adebe-109">Teams user-level licenses are managed directly through the Office 365 admin center user management interfaces.</span></span> <span data-ttu-id="adebe-110">Администратор может назначать лицензии для новых пользователей при создании их учетных записей, а также для пользователей с существующими учетными записями.</span><span class="sxs-lookup"><span data-stu-id="adebe-110">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="adebe-111">Для управления лицензиями Microsoft Teams нужны права администратора управления пользователями или глобального администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="adebe-111">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="adebe-112">Когда пользователю назначается номер SKU лицензии, например E3 или E5, он автоматически получает лицензию Microsoft Teams и права на использование этого продукта.</span><span class="sxs-lookup"><span data-stu-id="adebe-112">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams.</span></span> <span data-ttu-id="adebe-113">Администраторы могут детально управлять всеми лицензиями и службами Office 365, а также включать и отключать лицензию Microsoft Teams для отдельного пользователя или группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="adebe-113">Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Снимок экрана с разделом лицензий продуктов в Центре администрирования Office 365.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="adebe-115">В любое время можно отключить команды пользовательской лицензии.</span><span class="sxs-lookup"><span data-stu-id="adebe-115">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="adebe-116">После отключения лицензии, пользователям доступа к группами Майкрософт не сможет и пользователь больше не смогут видеть группами в запуска приложения для Office 365 и главной страницы.</span><span class="sxs-lookup"><span data-stu-id="adebe-116">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![Снимок экрана с разделом лицензий продуктов в Центре администрирования Office 365, где выбрана служба Microsoft Teams.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="adebe-118">Управление с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="adebe-118">Manage via PowerShell</span></span>

<span data-ttu-id="adebe-119">Включение и отключение в PowerShell лицензии на рабочую нагрузку Microsoft Teams выполняются точно так же, как и для других нагрузок.</span><span class="sxs-lookup"><span data-stu-id="adebe-119">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="adebe-120">План обслуживания для Microsof Teams называется TEAMS1.</span><span class="sxs-lookup"><span data-stu-id="adebe-120">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="adebe-121">Для государственных учреждений имя плана службы — TEAMS_GOV.</span><span class="sxs-lookup"><span data-stu-id="adebe-121">For Government the service plan name is TEAMS_GOV.</span></span> <span data-ttu-id="adebe-122">(Дополнительные сведения: [Отключение доступа к службам с помощью Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell).)</span><span class="sxs-lookup"><span data-stu-id="adebe-122">(See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="adebe-123">**Пример:** Ниже приведен краткий образца на как может отключить команды для всех пользователей определенного лицензию.</span><span class="sxs-lookup"><span data-stu-id="adebe-123">**Sample:** The following is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="adebe-124">Сначала выполните эту операцию, а затем отдельно активируйте лицензии для каждого пользователя, которому нужен доступ в рамках пилотной программы.</span><span class="sxs-lookup"><span data-stu-id="adebe-124">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="adebe-125">Чтобы отобразить типы подписок в вашей организации, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="adebe-125">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="adebe-126">Введите название плана, которое включает название организации и план для вашего образовательного заведения (например, ContosoSchool:ENTERPRISEPACK_STUDENT), после чего выполните следующие команды.</span><span class="sxs-lookup"><span data-stu-id="adebe-126">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="adebe-127">Чтобы отключить команды для всех пользователей с помощью активная лицензия для именованного плана, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="adebe-127">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Значок для точки принятия решений.](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="adebe-129">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="adebe-129">Decision Point</span></span>         |<ul><li><span data-ttu-id="adebe-130">Что такое план вашей организации для групп адаптация новых сотрудников в организации?</span><span class="sxs-lookup"><span data-stu-id="adebe-130">What is your organization’s plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="adebe-131">(в пилотном или открытом режиме)?</span><span class="sxs-lookup"><span data-stu-id="adebe-131">(Pilot or Open)</span></span></li></ul>         |
|![Значок дальнейших действий.](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="adebe-133">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="adebe-133">Next Steps</span></span>         |<ul><li><span data-ttu-id="adebe-134">Если адаптация новых сотрудников с помощью закрытой пилотного проекта, решить, если хотите сделать лицензирования или нацелено обмена данными.</span><span class="sxs-lookup"><span data-stu-id="adebe-134">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targeted communication.</span></span></li><li><span data-ttu-id="adebe-135">В зависимости от лица, выполните действия, чтобы убедитесь, что только пилотный проект пользователей, которые могут получить доступ к группам (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="adebe-135">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="adebe-136">Документирование рекомендаций для пользователей, которые, которым будет (или не работает) имеют доступ к группам.</span><span class="sxs-lookup"><span data-stu-id="adebe-136">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a><span data-ttu-id="adebe-137">Управление группами на уровне клиента Office 365</span><span class="sxs-lookup"><span data-stu-id="adebe-137">Manage Teams at the Office 365 tenant level</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

