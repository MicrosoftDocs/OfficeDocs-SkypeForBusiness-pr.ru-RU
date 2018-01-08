---
title: "Управление доступом пользователей к Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Сведения о том, как включить или отключить доступ на уровне пользователей для отдельных лиц."
ms.openlocfilehash: 66ec29077b83b799c85acce1b5869b82fb0b83f7
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2017
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="ccef2-103">Управление доступом пользователей к Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ccef2-103">Manage user access to Microsoft Teams</span></span>
=====================================

<span data-ttu-id="ccef2-104">Доступ к Microsoft Teams на уровне пользователей можно включать и отключать для отдельных лиц, назначая или удаляя лицензию на продукт Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ccef2-104">At the user-level, access to Microsoft Teams can be enabled of disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="ccef2-105">Другие параметры политики для полного или частичного включения или отключения функций Microsoft Teams на уровне отдельных пользователей сейчас отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="ccef2-105">Currently, there are no policy options for turning Microsoft Teams, or a subset of Microsoft Teams features on or off at an individual user level outside of licensing.</span></span>



> [!NOTE]
><span data-ttu-id="ccef2-106">Корпорация Майкрософт рекомендует включить Microsoft Teams для всех пользователей в организации, чтобы обеспечить согласованное формирование команд под проекты и другие инициативы.</span><span class="sxs-lookup"><span data-stu-id="ccef2-106">Microsoft recommends that Microsoft Teams is enabled for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="ccef2-107">Даже если вы хотите провести пилотный проект, все равно лучше включить Microsoft Teams для всех пользователей, ограничив доступ только к тестируемым функциям.</span><span class="sxs-lookup"><span data-stu-id="ccef2-107">Even if you are deciding to pilot, it may still be helpful to keep Microsoft Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

<span data-ttu-id="ccef2-108">Управление лицензиями Microsoft Teams на уровне пользователей осуществляется непосредственно через Центр администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="ccef2-108">Microsoft Teams user-level licenses are managed directly through the Office 365 admin center user management interfaces.</span></span> <span data-ttu-id="ccef2-109">Администратор может назначать лицензии для новых пользователей при создании их учетных записей, а также для пользователей с существующими учетными записями.</span><span class="sxs-lookup"><span data-stu-id="ccef2-109">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="ccef2-110">Для управления лицензиями Microsoft Teams нужны права администратора управления пользователями или глобального администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="ccef2-110">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="ccef2-111">Когда пользователю назначается номер SKU лицензии, например E3 или E5, он автоматически получает лицензию Microsoft Teams и права на использование этого продукта.</span><span class="sxs-lookup"><span data-stu-id="ccef2-111">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams.</span></span> <span data-ttu-id="ccef2-112">Администраторы могут детально управлять всеми лицензиями и службами Office 365, а также включать и отключать лицензию Microsoft Teams для отдельного пользователя или группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="ccef2-112">Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Снимок экрана с разделом лицензий продуктов в Центре администрирования Office 365.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="ccef2-114">Лицензию пользователя Microsoft Teams можно отключить в любое время.</span><span class="sxs-lookup"><span data-stu-id="ccef2-114">A Microsoft Teams user license can be disabled at any time.</span></span> <span data-ttu-id="ccef2-115">После этого пользователь не может получить доступ к Microsoft Teams, а также не видит Microsoft Teams на домашней странице и в средстве запуска приложений Office 365.</span><span class="sxs-lookup"><span data-stu-id="ccef2-115">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Microsoft Teams in the Office 365 app launcher and homepage.</span></span>

![Снимок экрана с разделом лицензий продуктов в Центре администрирования Office 365, где выбрана служба Microsoft Teams.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

<span data-ttu-id="ccef2-117">Кроме Центра администрирования Office 365, для назначения и удаления лицензий вы можете использовать PowerShell в Office 365.</span><span class="sxs-lookup"><span data-stu-id="ccef2-117">In addition to using the Office 365 admin center, Office 365 admins can also use Office 365 PowerShell to assign and remove licenses.</span></span> <span data-ttu-id="ccef2-118">Чтобы назначить лицензию пользователю, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ccef2-118">To assign a license to a user, use the following syntax:</span></span>

<span data-ttu-id="ccef2-119">Set-MsolUserLicense -UserPrincipalName "\<учетная_запись\>" -AddLicenses "\<код_SKU_учетной_записи\>"</span><span class="sxs-lookup"><span data-stu-id="ccef2-119">Set-MsolUserLicense -UserPrincipalName "\<Account\>" -AddLicenses "\<AccountSkuId\>"</span></span>

<span data-ttu-id="ccef2-120">Следующий пример назначает лицензию из плана лицензирования litwareinc:ENTERPRISEPACK (Office 365 корпоративный E3) пользователю без лицензии belindan@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="ccef2-120">The following example assigns a license from the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) licensing plan to the unlicensed user belindan@litwareinc.com.</span></span>

<span data-ttu-id="ccef2-121">Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"</span><span class="sxs-lookup"><span data-stu-id="ccef2-121">Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"</span></span>

<span data-ttu-id="ccef2-122">Дополнительные сведения и примеры см. в статье [*Назначение лицензий учетным записям пользователей с помощью PowerShell в Office 365*](https://go.microsoft.com/fwlink/?linkid=855755).</span><span class="sxs-lookup"><span data-stu-id="ccef2-122">For more details and examples, see [*Assign licenses to user accounts with Office 365 PowerShell*](https://go.microsoft.com/fwlink/?linkid=855755).</span></span>

<span data-ttu-id="ccef2-123">Чтобы удалить лицензию из существующей учетной записи пользователя, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ccef2-123">To remove licenses from an existing user account, use the following syntax:</span></span>

<span data-ttu-id="ccef2-124">Set-MsolUserLicense -UserPrincipalName \<учетная_запись\> -RemoveLicenses "\<код_SKU_учетной_записи_1\>", "\<код_SKU_учетной_записи_2\>"</span><span class="sxs-lookup"><span data-stu-id="ccef2-124">Set-MsolUserLicense -UserPrincipalName \<Account\> -RemoveLicenses "\<AccountSkuId1\>", "\<AccountSkuId2\>"</span></span>

<span data-ttu-id="ccef2-125">Следующий пример удаляет лицензию litwareinc:ENTERPRISEPACK (Office 365 корпоративный E3) из учетной записи пользователя BelindaN@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="ccef2-125">The following example removes the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) license from the user account BelindaN@litwareinc.com.</span></span>

<span data-ttu-id="ccef2-126">Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"</span><span class="sxs-lookup"><span data-stu-id="ccef2-126">Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"</span></span>

<span data-ttu-id="ccef2-127">Дополнительные сведения и примеры см. в статье [*Удаление лицензий из учетных записей пользователей с помощью PowerShell в Office 365*](https://go.microsoft.com/fwlink/?linkid=855756).</span><span class="sxs-lookup"><span data-stu-id="ccef2-127">For more details and examples, see [*Remove licenses from user accounts with office 365 PowerShell*](https://go.microsoft.com/fwlink/?linkid=855756).</span></span>

| | | |
|---------|---------|---------|
|![Значок для точки принятия решений.](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="ccef2-129">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="ccef2-129">Decision Point</span></span>         |<ul><li><span data-ttu-id="ccef2-130">Каков план вашей организации по повсеместной адаптации Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ccef2-130">What is your organization’s plan for Microsoft Teams onboarding across the organization?</span></span>  <span data-ttu-id="ccef2-131">(в пилотном или открытом режиме)?</span><span class="sxs-lookup"><span data-stu-id="ccef2-131">(Pilot or Open)</span></span></li></ul>         |
|![Значок дальнейших действий.](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="ccef2-133">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="ccef2-133">Next Steps</span></span>         |<ul><li><span data-ttu-id="ccef2-134">Если адаптация планируется в закрытом пилотном режиме, определите, будет ли это реализовано с помощью лицензирования либо адресного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="ccef2-134">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targetted communication.</span></span></li><li><span data-ttu-id="ccef2-135">При необходимости примите соответствующие меры, чтобы предоставить доступ к Microsoft Teams только пользователям пилотного проекта.</span><span class="sxs-lookup"><span data-stu-id="ccef2-135">Depending on decision, take steps to make sure only Pilot users who are allowed to access Microsoft Teams (if needed).</span></span></li><li><span data-ttu-id="ccef2-136">Задокументируйте указания относительно того, какие пользователи будут (или не будут) иметь доступ к Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ccef2-136">Document the guidelines for which users who will (or will not) have access to Microsoft Teams below.</span></span></li></ul>         |
