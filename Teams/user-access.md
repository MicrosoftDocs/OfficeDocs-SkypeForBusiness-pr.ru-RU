---
title: Управление доступом пользователей к Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
f1.keywords: ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.reviewer: ritikag
search.appverid: MET150
description: Сведения о том, как включить или отключить доступ на уровне пользователей для отдельных лиц.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ee7a8303ed9c46e1b60bbd3588fc36d754f773d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41707454"
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="1bcee-103">Управление доступом пользователей к Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1bcee-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="1bcee-104">На уровне пользователей доступ к Microsoft Teams можно включить или отключить отдельно для каждого пользователя с помощью назначения или удаления лицензии на продукт Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1bcee-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="1bcee-105">С помощью политик сообщений, управляемых из центра администрирования Teams, можно управлять тем, какие функции чата и обмена сообщениями в каналах доступны для пользователей в Teams.</span><span class="sxs-lookup"><span data-stu-id="1bcee-105">Use messaging policies, managed from the Teams Admin Center, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="1bcee-106">Вы можете использовать политику по умолчанию или создать одну или несколько настраиваемых политик обмена сообщениями для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1bcee-106">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="1bcee-107">Дополнительные сведения можно найти в статье [Управление политиками обмена сообщениями в Teams](messaging-policies-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="1bcee-107">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>

> [!NOTE]
><span data-ttu-id="1bcee-108">Корпорация Microsoft рекомендует включать команды для всех пользователей в компании, чтобы обеспечить согласованное формирование групп для проектов и других динамических инициатив.</span><span class="sxs-lookup"><span data-stu-id="1bcee-108">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="1bcee-109">Даже если вы решаете пилотный проект, может быть полезно, чтобы группа была включена для всех пользователей, но только Целевая связь с пилотной группой пользователей.</span><span class="sxs-lookup"><span data-stu-id="1bcee-109">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-teams-through-the-microsoft-365-admin-center"></a><span data-ttu-id="1bcee-110">Управление группами через центр администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1bcee-110">Manage Teams through the Microsoft 365 admin center</span></span>

<span data-ttu-id="1bcee-111">Управление лицензиями на уровне пользователей Teams осуществляется напрямую через интерфейсы управления пользователями в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1bcee-111">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="1bcee-112">Администратор может назначать лицензии для новых пользователей при создании их учетных записей, а также для пользователей с существующими учетными записями.</span><span class="sxs-lookup"><span data-stu-id="1bcee-112">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="1bcee-113">Для управления лицензиями Microsoft Teams нужны права администратора управления пользователями или глобального администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="1bcee-113">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="1bcee-114">Когда пользователю назначается номер SKU лицензии, например E3 или E5, он автоматически получает лицензию Microsoft Teams и права на использование этого продукта.</span><span class="sxs-lookup"><span data-stu-id="1bcee-114">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams.</span></span> <span data-ttu-id="1bcee-115">Администраторы могут детально управлять всеми лицензиями и службами Office 365, а также включать и отключать лицензию Microsoft Teams для отдельного пользователя или группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="1bcee-115">Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Снимок экрана: раздел "лицензии на продукты" в центре администрирования.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="1bcee-117">Лицензия пользователя Teams может быть отключена в любое время.</span><span class="sxs-lookup"><span data-stu-id="1bcee-117">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="1bcee-118">После отключения лицензии пользователи смогут получить доступ к Microsoft Teams, и пользователь больше не сможет просматривать команды в средстве запуска приложений Office 365 и на домашней странице.</span><span class="sxs-lookup"><span data-stu-id="1bcee-118">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![Снимок экрана, на котором показаны команды, выбранные в разделе "лицензии на продукты".](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="1bcee-120">Управление через PowerShell</span><span class="sxs-lookup"><span data-stu-id="1bcee-120">Manage via PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1bcee-121">New-Мсоллиценсеоптионс включит все службы, которые ранее были отключены, если они не были явно идентифицированы в пользовательском сценарии.</span><span class="sxs-lookup"><span data-stu-id="1bcee-121">New-MsolLicenseOptions will enable all services that were previously disabled unless explicitly identified in your customized script.</span></span> <span data-ttu-id="1bcee-122">Например, если вы хотите покинуть публикацию Exchange & Sway при дополнительном отключении Teams, вам потребуется включить эту функцию в сценарий или оба варианта Exchange & Sway будут включены для указанных вами пользователей.</span><span class="sxs-lookup"><span data-stu-id="1bcee-122">As an example, if you wanted to leave both Exchange & Sway disabled while additionally disabling Teams, you'd need to include this in the script or both Exchange & Sway will become enabled for those users you've identified.</span></span> <span data-ttu-id="1bcee-123">Чтобы использовать графический интерфейс для управления этими функциональными возможностями, ознакомьтесь с дополнительными сведениями [в разделе средства создания отчетов и управления лицензиями Office 365 – Назначение лицензий на удаление для массовой](https://gallery.technet.microsoft.com/Office365-License-cfd9489c) информации.</span><span class="sxs-lookup"><span data-stu-id="1bcee-123">To use a GUI to manage this functionality, see [Office 365 License Reporting and Management Tool -Assign Remove Licenses in Bulk](https://gallery.technet.microsoft.com/Office365-License-cfd9489c) for more information.</span></span>

<span data-ttu-id="1bcee-124">Включение и отключение в PowerShell лицензии на рабочую нагрузку Microsoft Teams выполняются точно так же, как и для других нагрузок.</span><span class="sxs-lookup"><span data-stu-id="1bcee-124">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="1bcee-125">План обслуживания для Microsof Teams называется TEAMS1.</span><span class="sxs-lookup"><span data-stu-id="1bcee-125">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="1bcee-126">Для GCC не TEAMS_GOV имя плана обслуживания.</span><span class="sxs-lookup"><span data-stu-id="1bcee-126">For GCC the service plan name is TEAMS_GOV.</span></span> <span data-ttu-id="1bcee-127">Для GCC High имя плана обслуживания TEAMS_GCCHIGH.</span><span class="sxs-lookup"><span data-stu-id="1bcee-127">For GCC High the service plan name is TEAMS_GCCHIGH.</span></span> <span data-ttu-id="1bcee-128">Для вызова по требованию имя плана обслуживания TEAMS_DOD (Дополнительные сведения можно найти в разделе [Отключение доступа к службам с помощью Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) .)</span><span class="sxs-lookup"><span data-stu-id="1bcee-128">For DoD the service plan name is TEAMS_DOD (See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="1bcee-129">**Пример:** Ниже приведен краткий пример того, как отключить группы для всех пользователей определенного типа лицензии.</span><span class="sxs-lookup"><span data-stu-id="1bcee-129">**Sample:** The following is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="1bcee-130">Сначала выполните эту операцию, а затем отдельно активируйте лицензии для каждого пользователя, которому нужен доступ в рамках пилотной программы.</span><span class="sxs-lookup"><span data-stu-id="1bcee-130">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="1bcee-131">Чтобы отобразить типы подписок в вашей организации, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="1bcee-131">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="1bcee-132">Введите название плана, которое включает название организации и план для вашего образовательного заведения (например, ContosoSchool:ENTERPRISEPACK_STUDENT), после чего выполните следующие команды.</span><span class="sxs-lookup"><span data-stu-id="1bcee-132">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="1bcee-133">Чтобы отключить команды для всех пользователей с активной лицензией на именованный план, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1bcee-133">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Значок, представляющий точку принятия решения](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="1bcee-135">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="1bcee-135">Decision Point</span></span>         |<ul><li><span data-ttu-id="1bcee-136">Каков план Организации для Teams по всей Организации?</span><span class="sxs-lookup"><span data-stu-id="1bcee-136">What is your organization’s plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="1bcee-137">(в пилотном или открытом режиме)?</span><span class="sxs-lookup"><span data-stu-id="1bcee-137">(Pilot or Open)</span></span></li></ul>         |
|![Значок, представляющий следующие шаги](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="1bcee-139">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="1bcee-139">Next Steps</span></span>         |<ul><li><span data-ttu-id="1bcee-140">Если вы выполняете предварительную подплату в закрытом пилотном проекте, решите, нужно ли это сделать с помощью лицензирования или для целей предустановления связи.</span><span class="sxs-lookup"><span data-stu-id="1bcee-140">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targeted communication.</span></span></li><li><span data-ttu-id="1bcee-141">В зависимости от решения примите меры, чтобы убедиться, что только пилотные пользователи, которым разрешен доступ к Teams (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="1bcee-141">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="1bcee-142">Задокументируйте рекомендации для пользователей, которые будут (или не будут) иметь доступ к Teams.</span><span class="sxs-lookup"><span data-stu-id="1bcee-142">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a><span data-ttu-id="1bcee-143">Управление группами на уровне клиентов Office 365</span><span class="sxs-lookup"><span data-stu-id="1bcee-143">Manage Teams at the Office 365 tenant level</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

