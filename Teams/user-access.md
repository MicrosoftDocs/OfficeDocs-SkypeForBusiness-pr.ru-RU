---
title: Управление доступом пользователей к Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: Сведения о том, как включить или отключить доступ на уровне пользователей для отдельных лиц.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: a612420808af06a773d206573f02d805aac06b15
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="f8edd-103">Управление доступом пользователей к Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f8edd-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="f8edd-104">На уровне пользователя доступ к группами Майкрософт могут включаться и отключаться на уровне пользователя с назначение или удаление лицензии группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f8edd-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="f8edd-105">На данный момент нет способа политики для включения группы или подмножество функций группам включено или отключено на уровне отдельных пользователей за пределами лицензирования.</span><span class="sxs-lookup"><span data-stu-id="f8edd-105">Currently, there are no policy options for turning Teams, or a subset of Teams features, on or off at an individual user level outside of licensing.</span></span>

> [!NOTE]
><span data-ttu-id="f8edd-106">Корпорация Майкрософт рекомендует включить групп для всех пользователей в организации, чтобы команды может быть создана согласованным образом: для проектов и других динамических инициатив.</span><span class="sxs-lookup"><span data-stu-id="f8edd-106">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="f8edd-107">Даже в том случае, если принято решение о для пилотного, может быть полезно сохранить групп, включено для всех пользователей, но только предназначенных для коммуникаций для пилотной группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="f8edd-107">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-directly-through-the-office-365-admin-center"></a><span data-ttu-id="f8edd-108">Управление непосредственно через Центр администрирования Office 365</span><span class="sxs-lookup"><span data-stu-id="f8edd-108">Manage directly through the Office 365 admin center</span></span>

<span data-ttu-id="f8edd-109">Лицензий на уровне пользователей группам осуществляется непосредственно через Центр администрирования Office 365 пользовательских интерфейсов управления.</span><span class="sxs-lookup"><span data-stu-id="f8edd-109">Teams user-level licenses are managed directly through the Office 365 admin center user management interfaces.</span></span> <span data-ttu-id="f8edd-110">Администратор может назначать лицензии для новых пользователей при создании их учетных записей, а также для пользователей с существующими учетными записями.</span><span class="sxs-lookup"><span data-stu-id="f8edd-110">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="f8edd-111">Для управления лицензиями Microsoft Teams нужны права администратора управления пользователями или глобального администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="f8edd-111">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="f8edd-112">Когда пользователю назначается номер SKU лицензии, например E3 или E5, он автоматически получает лицензию Microsoft Teams и права на использование этого продукта.</span><span class="sxs-lookup"><span data-stu-id="f8edd-112">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams.</span></span> <span data-ttu-id="f8edd-113">Администраторы могут детально управлять всеми лицензиями и службами Office 365, а также включать и отключать лицензию Microsoft Teams для отдельного пользователя или группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="f8edd-113">Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Снимок экрана с разделом лицензий продуктов в Центре администрирования Office 365.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="f8edd-115">В любое время можно отключить команды пользовательской лицензии.</span><span class="sxs-lookup"><span data-stu-id="f8edd-115">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="f8edd-116">После отключения лицензии, пользователям доступа к группами Майкрософт не сможет и пользователь больше не смогут видеть группами в запуска приложения для Office 365 и главной страницы.</span><span class="sxs-lookup"><span data-stu-id="f8edd-116">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![Снимок экрана с разделом лицензий продуктов в Центре администрирования Office 365, где выбрана служба Microsoft Teams.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="f8edd-118">Управление с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8edd-118">Manage via PowerShell</span></span>

<span data-ttu-id="f8edd-119">Включение и отключение в PowerShell лицензии на рабочую нагрузку Microsoft Teams выполняются точно так же, как и для других нагрузок.</span><span class="sxs-lookup"><span data-stu-id="f8edd-119">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="f8edd-120">План обслуживания для Microsof Teams называется TEAMS1.</span><span class="sxs-lookup"><span data-stu-id="f8edd-120">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="f8edd-121">(Дополнительные сведения: [Отключение доступа к службам с помощью Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell).)</span><span class="sxs-lookup"><span data-stu-id="f8edd-121">(See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="f8edd-122">**Пример:** Ниже приведен только краткий образец на как может отключить команды для всех пользователей определенного лицензию.</span><span class="sxs-lookup"><span data-stu-id="f8edd-122">**Sample:** Below is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="f8edd-123">Сначала выполните эту операцию, а затем отдельно активируйте лицензии для каждого пользователя, которому нужен доступ в рамках пилотной программы.</span><span class="sxs-lookup"><span data-stu-id="f8edd-123">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="f8edd-124">Чтобы отобразить типы подписок в вашей организации, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="f8edd-124">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="f8edd-125">Введите название плана, которое включает название организации и план для вашего образовательного заведения (например, ContosoSchool:ENTERPRISEPACK_STUDENT), после чего выполните следующие команды.</span><span class="sxs-lookup"><span data-stu-id="f8edd-125">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="f8edd-126">Чтобы отключить команды для всех пользователей с помощью активная лицензия для именованного плана, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f8edd-126">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Значок для точки принятия решений.](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="f8edd-128">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="f8edd-128">Decision Point</span></span>         |<ul><li><span data-ttu-id="f8edd-129">Что такое план вашей организации для групп адаптация новых сотрудников в организации?</span><span class="sxs-lookup"><span data-stu-id="f8edd-129">What is your organization’s plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="f8edd-130">(в пилотном или открытом режиме)?</span><span class="sxs-lookup"><span data-stu-id="f8edd-130">(Pilot or Open)</span></span></li></ul>         |
|![Значок дальнейших действий.](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="f8edd-132">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="f8edd-132">Next Steps</span></span>         |<ul><li><span data-ttu-id="f8edd-133">Если адаптация планируется в закрытом пилотном режиме, определите, будет ли это реализовано с помощью лицензирования либо адресного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="f8edd-133">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targetted communication.</span></span></li><li><span data-ttu-id="f8edd-134">В зависимости от лица, выполните действия, чтобы убедитесь, что только пилотный проект пользователей, которые могут получить доступ к группам (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="f8edd-134">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="f8edd-135">Документирование рекомендаций для пользователей, которые, которым будет (или не работает) имеют доступ к группам.</span><span class="sxs-lookup"><span data-stu-id="f8edd-135">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-via-office-sku-level-switch"></a><span data-ttu-id="f8edd-136">Управление через коммутатор уровня Office Sku</span><span class="sxs-lookup"><span data-stu-id="f8edd-136">Manage via Office Sku level switch</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

1.  <span data-ttu-id="f8edd-137">Войдите в [Центр администрирования Office 365](https://go.microsoft.com/fwlink/?linkid=854614) по учетной записи, имеющей права глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="f8edd-137">Sign in to the [Office 365 Admin center](https://go.microsoft.com/fwlink/?linkid=854614) with an account that has Global Administrator privileges.</span></span>

2.  <span data-ttu-id="f8edd-138">Перейдите в раздел **Параметры** > **Службы и надстройки**.</span><span class="sxs-lookup"><span data-stu-id="f8edd-138">Go to **Settings** > **Services & add-ins**.</span></span>

    ![<span data-ttu-id="f8edd-139">Снимок экрана с разделом параметров в Центре администрирования Office 365, где выбран пункт "Services & add-ins" (Службы и надстройки).</span><span class="sxs-lookup"><span data-stu-id="f8edd-139">Screenshot of the Settings section in the Office 365 admin center with Services & add-ins selected.</span></span> ](media/Set_up_Microsoft_Teams_in_your_Office_365_organization_image1.png)

3.  <span data-ttu-id="f8edd-140">На странице "Services & add-ins" (Службы и надстройки) щелкните **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="f8edd-140">On the Services & add-ins page, click **Microsoft Teams**.</span></span>

    ![Снимок экрана со страницей "Services & add-ins" (Службы и надстройки), где выбрана служба Microsoft Teams.](media/Set_up_Microsoft_Teams_in_your_Office_365_organization_image2.png)

4.  <span data-ttu-id="f8edd-142">Чтобы включить Microsoft Teams для организации, воспользуйтесь средством выбора лицензий. Выберите все нужные лицензии, активируйте переключатель **Вкл**, а затем щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f8edd-142">To turn on Teams for the organization use the license picker and select each license then set the toggle to **On** and then click **Save**.</span></span>

    ![Снимок экрана со страницей параметров Microsoft Teams, где эта служба включена с помощью переключателя.](media/Services-and-addins-control-Microsoft-Teams.PNG)
