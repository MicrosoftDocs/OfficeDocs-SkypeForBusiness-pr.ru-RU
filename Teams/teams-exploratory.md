---
title: Управление предложением Microsoft Teams Exploratory
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Пользователи Microsoft 365 или Office 365 без лицензии на Microsoft Teams могут воспользоваться лицензией на Exploratory Teams.
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb5e415128baae6bfc458b5d0000128010a9b5cd
ms.sourcegitcommit: 71b9b5ec80014bd25758493bc06d633c4eac735c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2021
ms.locfileid: "50867048"
---
# <a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="31f4e-103">Управление лицензией на Microsoft Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="31f4e-103">Manage the Microsoft Teams Exploratory license</span></span>

<span data-ttu-id="31f4e-104">Предложение Microsoft Teams Exploratory позволяет пользователям в вашей организации с лицензией на Azure Active Directory (Azure AD) и без лицензии на Teams оформить лицензию на Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="31f4e-104">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (Azure AD) and aren't licensed for Teams initiate an exploratory experience of Teams.</span></span> <span data-ttu-id="31f4e-105">Администраторы могут включать и отключать эту функцию для пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="31f4e-105">Admins can switch this feature on or off for users in their organization.</span></span> <span data-ttu-id="31f4e-106">Предыдущее предложение [Microsoft Commercial Cloud Trial](iw-trial-teams.md) заменено предложением Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="31f4e-106">The earlier [Microsoft Commercial Cloud Trial](iw-trial-teams.md) is now replaced by the Teams Exploratory experience.</span></span>

> [!NOTE]
> <span data-ttu-id="31f4e-107">Существует ограничение в 100 лицензий Microsoft Teams Exploratory на клиент.</span><span class="sxs-lookup"><span data-stu-id="31f4e-107">There is a limit of 100 Microsoft Teams Exploratory licenses per tenant.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="31f4e-108">Что включает предложение Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="31f4e-108">What's in the Teams Exploratory experience</span></span>

<span data-ttu-id="31f4e-109">Администратору будут представлены следующие планы обслуживания, входящие в предложение Teams Exploratory:</span><span class="sxs-lookup"><span data-stu-id="31f4e-109">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>

- <span data-ttu-id="31f4e-110">Exchange Online (план 1)</span><span class="sxs-lookup"><span data-stu-id="31f4e-110">Exchange Online (Plan 1)</span></span>
- <span data-ttu-id="31f4e-111">Flow для Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="31f4e-111">Flow for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="31f4e-112">MyAnalytics для анализа данных</span><span class="sxs-lookup"><span data-stu-id="31f4e-112">Insights by MyAnalytics</span></span>
- <span data-ttu-id="31f4e-113">Microsoft Forms (план E1)</span><span class="sxs-lookup"><span data-stu-id="31f4e-113">Microsoft Forms (Plan E1)</span></span>
- <span data-ttu-id="31f4e-114">Планировщик (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="31f4e-114">Microsoft Planner</span></span>
- <span data-ttu-id="31f4e-115">Поиск (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="31f4e-115">Microsoft Search</span></span>
- <span data-ttu-id="31f4e-116">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="31f4e-116">Microsoft StaffHub</span></span>
- <span data-ttu-id="31f4e-117">Microsoft Stream для SKU Microsoft 365 и Office 365 E1 <sup>1</1></span><span class="sxs-lookup"><span data-stu-id="31f4e-117">Microsoft Stream for Microsoft 365 and Office 365 E1 SKUs <sup>1</1></span></span>
- <span data-ttu-id="31f4e-118">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="31f4e-118">Microsoft Teams</span></span>
- <span data-ttu-id="31f4e-119">Управление мобильными устройствами для Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="31f4e-119">Mobile Device Management for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="31f4e-120">Приложения Office Mobile для Office 365</span><span class="sxs-lookup"><span data-stu-id="31f4e-120">Office Mobile Apps for Office 365</span></span>
- <span data-ttu-id="31f4e-121">Office Online</span><span class="sxs-lookup"><span data-stu-id="31f4e-121">Office Online</span></span>
- <span data-ttu-id="31f4e-122">PowerApps для Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="31f4e-122">PowerApps for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="31f4e-123">SharePoint Online (план 1)</span><span class="sxs-lookup"><span data-stu-id="31f4e-123">SharePoint Online (Plan 1)</span></span>
- <span data-ttu-id="31f4e-124">Sway</span><span class="sxs-lookup"><span data-stu-id="31f4e-124">Sway</span></span>
- <span data-ttu-id="31f4e-125">To-Do (план 1)</span><span class="sxs-lookup"><span data-stu-id="31f4e-125">To-Do (Plan 1)</span></span>
- <span data-ttu-id="31f4e-126">Доска (план 1)</span><span class="sxs-lookup"><span data-stu-id="31f4e-126">Whiteboard (Plan 1)</span></span>
- <span data-ttu-id="31f4e-127">Yammer корпоративный</span><span class="sxs-lookup"><span data-stu-id="31f4e-127">Yammer Enterprise</span></span>

  <span data-ttu-id="31f4e-128"><sup>1</sup> Переход с использования Microsoft Stream на [OneDrive для бизнеса и SharePoint для записей собраний](tmr-meeting-recording-change.md) будет поэтапным процессом.</span><span class="sxs-lookup"><span data-stu-id="31f4e-128"><sup>1</sup> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach.</span></span> <span data-ttu-id="31f4e-129">При запуске вы сможете согласиться на это предложение.</span><span class="sxs-lookup"><span data-stu-id="31f4e-129">At launch, you'll be able to opt in to this experience.</span></span> <span data-ttu-id="31f4e-130">В ноябре вам придется отказаться, если вы хотите продолжить использовать Stream.</span><span class="sxs-lookup"><span data-stu-id="31f4e-130">In November, you'll have to opt out if you want to continue using Stream.</span></span> <span data-ttu-id="31f4e-131">В начале 2021 г. все клиенты должны будут использовать OneDrive для бизнеса и SharePoint для записи новых собраний.</span><span class="sxs-lookup"><span data-stu-id="31f4e-131">Sometime in early 2021, we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

## <a name="whos-eligible"></a><span data-ttu-id="31f4e-132">Кто имеет право на использование</span><span class="sxs-lookup"><span data-stu-id="31f4e-132">Who's eligible</span></span>

<span data-ttu-id="31f4e-133">Пользователи соответствуют критериям Teams Exploratory, если они:</span><span class="sxs-lookup"><span data-stu-id="31f4e-133">Users fit the criteria for a Teams Exploratory experience if they:</span></span>

- <span data-ttu-id="31f4e-134">Имеют адрес электронной почты с управляемым доменом Azure AD.</span><span class="sxs-lookup"><span data-stu-id="31f4e-134">Have a managed Azure AD domain email address.</span></span>
- <span data-ttu-id="31f4e-135">Входят в состав клиента с платной подпиской.</span><span class="sxs-lookup"><span data-stu-id="31f4e-135">Belong to a tenant with a paid subscription.</span></span>
- <span data-ttu-id="31f4e-136">У вас нет действующей лицензии на Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="31f4e-136">Do not have an active Teams license.</span></span>
- <span data-ttu-id="31f4e-137">Не в клиенте, где была создана политика назначения лицензии.</span><span class="sxs-lookup"><span data-stu-id="31f4e-137">Are not in a tenant where a license assignment policy was created.</span></span>

<span data-ttu-id="31f4e-p103">У пользователей есть возможность зарегистрироваться для получения приложений и пробных версий (в Центре администрирования Microsoft 365). Дополнительные сведения см. в разделе [Управление предложением Teams Exploratory](#manage-the-teams-exploratory-experience) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="31f4e-p103">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center). For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span>

## <a name="who-isnt-eligible"></a><span data-ttu-id="31f4e-140">Кто не имеет права на использование</span><span class="sxs-lookup"><span data-stu-id="31f4e-140">Who isn't eligible</span></span>

<span data-ttu-id="31f4e-141">Пользователи не соответствуют критериям, если они:</span><span class="sxs-lookup"><span data-stu-id="31f4e-141">Users don't fit the criteria if they:</span></span>

- <span data-ttu-id="31f4e-142">Имеют или ранее имели платную, бесплатную или пробную лицензию на Teams.</span><span class="sxs-lookup"><span data-stu-id="31f4e-142">Currently or previously had Teams from a paid, unpaid, or trial license</span></span>
- <span data-ttu-id="31f4e-143">Входят в состав клиента, который использовал/получил по крайней мере одно специальное предложение, связанное с COVID.</span><span class="sxs-lookup"><span data-stu-id="31f4e-143">Are in a tenant that used/received at least one special COVID offer.</span></span>

<span data-ttu-id="31f4e-144">Ваша организация не может использовать это предложение, если вы являетесь клиентом партнера по синдикации или клиентом GCC, GCC High, DoD либо EDU.</span><span class="sxs-lookup"><span data-stu-id="31f4e-144">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="31f4e-145">Регистрация для получения Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="31f4e-145">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="31f4e-146">Подходящие пользователи могут зарегистрироваться для получения предложения Teams Exploratory, выполнив вход в Teams в классической или веб-версии ([teams.microsoft.com](https://teams.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="31f4e-146">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams from the desktop or web ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="31f4e-147">В настоящее время включение предложения Exploratory в мобильной версии не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="31f4e-147">At this time, enabling Exploratory through mobile is not supported.</span></span> <span data-ttu-id="31f4e-148">При регистрации им будет автоматически назначена лицензия, и администратор клиента получит соответствующее уведомление по электронной почте, когда пользователь организации в первый раз запустит Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="31f4e-148">When they sign up, they'll be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="31f4e-149">Управление предложением Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="31f4e-149">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="31f4e-150">Предложение Teams Exploratory предназначено для активации отдельными пользователями, и вы не можете активировать его от имени сотрудников, являющихся конечными пользователями.</span><span class="sxs-lookup"><span data-stu-id="31f4e-150">The Teams Exploratory experience is meant to be initiated by individual end users, and you can't initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="31f4e-p105">Предложение Teams Exploratory включает лицензию на Exchange Online, но она должна быть назначена пользователю администратором. Если у пользователя нет лицензии на Exchange, а администратор еще не назначил лицензию на Exchange Online, пользователь не сможет планировать собрания в Teams и использовать другие функции Teams.</span><span class="sxs-lookup"><span data-stu-id="31f4e-p105">The Teams Exploratory experience comes with an Exchange Online license, but it won't be assigned to the user until the admin assigns it. If the user doesn't have an Exchange license already, and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and might be missing other Teams functionality.</span></span>

<span data-ttu-id="31f4e-153">Администраторы могут отключить возможность использования Teams Exploratory для пользователей в своей организации с помощью переключателя **Пробные версии приложений и служб**.</span><span class="sxs-lookup"><span data-stu-id="31f4e-153">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>

### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="31f4e-154">Запрет на установку пользователями пробных версий приложений и служб</span><span class="sxs-lookup"><span data-stu-id="31f4e-154">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="31f4e-155">Вы можете отключить возможность установки пробных версий приложений и служб, чтобы пользователи не могли использовать Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="31f4e-155">You can turn off a user's ability to install trial apps and services, which would prevent the user from running the Teams Exploratory experience.</span></span>

1. <span data-ttu-id="31f4e-156">В Центре администрирования Microsoft 365 выберите **Параметры** > **Параметры организации**, щелкните **Службы** и нажмите **Приложения и службы, лицензированные для отдельных пользователей**.</span><span class="sxs-lookup"><span data-stu-id="31f4e-156">From the Microsoft 365 admin center, go to **Settings** > **Org settings**, select **Services**, and then select **User owned apps and services**.</span></span>

    ![страница "Службы" в Центре администрирования](media/iw-trial-services.png)

2. <span data-ttu-id="31f4e-158">Снимите флажок **Разрешить пользователям устанавливать пробные версии приложений и служб**.</span><span class="sxs-lookup"><span data-stu-id="31f4e-158">Clear the check mark from **Let users install trial apps and services**.</span></span>

    ![страница "Приложения и службы, лицензированные для отдельных пользователей" в Центре администрирования](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="31f4e-160">Если ваша организация не имеет права на использование Teams Exploratory, параметр **Разрешить пользователям устанавливать пробные версии приложений и служб** будет отсутствовать.</span><span class="sxs-lookup"><span data-stu-id="31f4e-160">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="31f4e-161">Управление доступностью для пользователя с лицензией, включающей Teams</span><span class="sxs-lookup"><span data-stu-id="31f4e-161">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="31f4e-p106">Пользователь, которому назначена лицензия, включающая Teams, не имеет права на использование Teams Exploratory. Если план обслуживания Teams включен, пользователь может выполнить вход в систему и использовать Teams. Если план обслуживания отключен, пользователь не может выполнить вход в систему и возможности Teams Exploratory ему недоступны. У вас должны быть права администратора.</span><span class="sxs-lookup"><span data-stu-id="31f4e-p106">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience. When the Teams service plan is turned on, the user can sign in and use Teams. If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available. You must have admin privileges.</span></span>

<span data-ttu-id="31f4e-166">Отключение доступа к Teams:</span><span class="sxs-lookup"><span data-stu-id="31f4e-166">To turn off access to Teams:</span></span>

1. <span data-ttu-id="31f4e-167">В Центре администрирования Microsoft 365 выберите **Пользователи** > **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="31f4e-167">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="31f4e-168">Установите флажок рядом с именем пользователя.</span><span class="sxs-lookup"><span data-stu-id="31f4e-168">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="31f4e-169">В правой части строки **Лицензии на продукты** щелкните ссылку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="31f4e-169">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="31f4e-170">В области **Лицензии на продукты** установите переключатель в положение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="31f4e-170">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![страница "Лицензии на продукты" в Центре администрирования.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="31f4e-172">Управление доступностью Teams для пользователей, уже использующих Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="31f4e-172">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="31f4e-p107">Если пользователь использует предложение Teams Exploratory, вы можете отключить его, удалив лицензию или план обслуживания. У вас должны быть права администратора.</span><span class="sxs-lookup"><span data-stu-id="31f4e-p107">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan. You must have admin privileges.</span></span>

<span data-ttu-id="31f4e-175">Чтобы отключить лицензию на Teams Exploratory, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="31f4e-175">To turn off the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="31f4e-176">В Центре администрирования Microsoft 365 выберите **Пользователи** > **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="31f4e-176">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="31f4e-177">Установите флажок рядом с именем пользователя.</span><span class="sxs-lookup"><span data-stu-id="31f4e-177">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="31f4e-178">В правой части строки **Лицензии на продукты** щелкните ссылку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="31f4e-178">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="31f4e-179">В области **Лицензии на продукты** установите переключатель для лицензии на это предложение в положение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="31f4e-179">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="31f4e-180">Переключатель для Teams Exploratory отобразится после того, как первый пользователь в организации запустит это предложение.</span><span class="sxs-lookup"><span data-stu-id="31f4e-180">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="31f4e-181">Управление Teams для пользователей с лицензией на Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="31f4e-181">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="31f4e-p108">Управление пользователями, у которых есть лицензия Teams Exploratory, аналогично управлению пользователями с обычной платной лицензией. Дополнительные сведения см. в разделе [Управление параметрами Teams в организации](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="31f4e-p108">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license. For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-the-teams-exploratory-license"></a><span data-ttu-id="31f4e-184">Перевод пользователей с лицензии Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="31f4e-184">Upgrade users from the Teams Exploratory license</span></span>

<span data-ttu-id="31f4e-185">Чтобы перевести пользователей с лицензии Teams Exploratory (у вас должны быть права администратора), выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="31f4e-185">To upgrade users from the Teams Exploratory license (you must have admin privileges), do the following tasks:</span></span>

1. <span data-ttu-id="31f4e-186">Приобретите подписку, в которую входит Teams.</span><span class="sxs-lookup"><span data-stu-id="31f4e-186">Purchase a subscription that includes Teams.</span></span>

2. <span data-ttu-id="31f4e-187">Удалите подписку пользователя на Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="31f4e-187">Remove the Teams Exploratory subscription from the user.</span></span>

3. <span data-ttu-id="31f4e-188">Назначьте приобретенную лицензию.</span><span class="sxs-lookup"><span data-stu-id="31f4e-188">Assign the newly purchased license.</span></span>

<span data-ttu-id="31f4e-189">Для получения дополнительной информации см. [Описание службы Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="31f4e-189">For more information, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

> [!NOTE]
> <span data-ttu-id="31f4e-p109">Если срок действия лицензии на Teams Exploratory закончится и пользователь сразу не перейдет на подписку, включающую Teams, у пользователя будет 30 дней льготного периода, а затем еще 30 дней, после чего данные будут удалены. Пользователь по-прежнему будет существовать в Azure Active Directory. После того, как пользователю будет назначена новая лицензия для повторного включения функций Teams, содержимое будет по-прежнему существовать, если пользователь будет добавлен в течение льготного периода.</span><span class="sxs-lookup"><span data-stu-id="31f4e-p109">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, they have 30 days of grace period and then another 30 days after which time the data is going to be deleted. The user still exists in Azure Active Directory. Once a new license is assigned to the user to enable Teams functionality again, all content will still exist if the user is added within the grace period time frame.</span></span>

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a><span data-ttu-id="31f4e-193">Что произойдет с устаревшими лицензиями на Microsoft Teams Commercial Cloud Trial</span><span class="sxs-lookup"><span data-stu-id="31f4e-193">What happens to legacy Microsoft Teams Commercial Cloud Trial licenses</span></span>

<span data-ttu-id="31f4e-p110">С февраля 2020 г. соответствующие критериям пользователи могут начать работу с последней версией Microsoft Teams Exploratory. Все устаревшие лицензии на Teams Commercial Cloud Trial будут автоматически преобразованы в лицензии на новое предложение до истечения срока действия пробной версии.</span><span class="sxs-lookup"><span data-stu-id="31f4e-p110">As of February 2020, eligible users can begin using the latest Microsoft Teams Exploratory experience. All legacy Teams Commercial Cloud Trial licenses will be automatically converted to the new offer before their trial expires.</span></span>

<span data-ttu-id="31f4e-p111">При первом входе пользователя в Teams Commercial Cloud Trial с истекшим сроком действия этому пользователю автоматически назначается лицензия на использование Teams Exploratory. Конвертация не происходит, пока пользователь не выполнит вход в систему.</span><span class="sxs-lookup"><span data-stu-id="31f4e-p111">When users sign in to their expired Teams Commercial Cloud Trial for the first time, we automatically assign a Teams Exploratory experience license to those users. Users aren't converted until they sign in.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="31f4e-198">Удаление лицензии на Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="31f4e-198">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="31f4e-199">Если вы хотите удалить эту лицензию с помощью PowerShell, см. статью [Использование PowerShell в Office 365 для удаления лицензий из учетных записей пользователей](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="31f4e-199">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="31f4e-200">Если вы хотите удалить эту лицензию на портале администрирования, см. статью [Удаление пользователя из организации](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span><span class="sxs-lookup"><span data-stu-id="31f4e-200">If you would like to remove this license through the admin portal, see: [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span></span>

## <a name="what-is-the-data-retention-policy"></a><span data-ttu-id="31f4e-201">Что такое политика хранения данных</span><span class="sxs-lookup"><span data-stu-id="31f4e-201">What is the data retention policy</span></span>

<span data-ttu-id="31f4e-202">См. [Сведения о подписке на Microsoft 365](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="31f4e-202">See [Microsoft 365 subscription information](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="31f4e-203">Срок действия предложения Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="31f4e-203">How long does the Teams Exploratory experience last</span></span>

<span data-ttu-id="31f4e-204">На начало 2021 года версия Teams Exploratory доступна в качестве подписки на 12 месяцев (от первоначальной регистрации пользователя) для всех новых клиентов.</span><span class="sxs-lookup"><span data-stu-id="31f4e-204">As of early 2021, Teams Exploratory is available as a 12 month subscription (from initial user sign-up) for all new customers.</span></span> <span data-ttu-id="31f4e-205">Новая подписка на версию Teams Exploratory начинается, когда первый пользователь в организации регистрируется в Teams Exploratory, и истекает через 12 месяцев.</span><span class="sxs-lookup"><span data-stu-id="31f4e-205">The new Teams Exploratory subscription starts when the first user in an organization signs-up for Teams Exploratory and it will expire after 12 months.</span></span> <span data-ttu-id="31f4e-206">Ко всем пользователям в одном клиенте применяется одинаковая дата окончания 12-месячного периода, который начинается с даты регистрации первого пользователя.</span><span class="sxs-lookup"><span data-stu-id="31f4e-206">The expiry date will apply to all users in the same tenant as the 12-month term begins on the first user's sign-up date.</span></span>

> [!NOTE]
> <span data-ttu-id="31f4e-207">Дата окончания взаимодействия настраивается на уровне организации, то есть она будет применена ко всем пользователям в этой организации.</span><span class="sxs-lookup"><span data-stu-id="31f4e-207">The end date for the experience is configured at an organization level, meaning it will apply to all users in the same organization.</span></span> <span data-ttu-id="31f4e-208">Например, Пользователь 1 регистрирует подписку 1 января 2021 года.</span><span class="sxs-lookup"><span data-stu-id="31f4e-208">For example, User 1 signs up for the subscription on January 1, 2021.</span></span> <span data-ttu-id="31f4e-209">Это устанавливает дату окончания подписки — 31 декабря 2021 года.</span><span class="sxs-lookup"><span data-stu-id="31f4e-209">This initiates a subscription end-date of December 31, 2021.</span></span> <span data-ttu-id="31f4e-210">Другой пользователь, Пользователь 2, регистрирует подписку 1 октября 2021 года.</span><span class="sxs-lookup"><span data-stu-id="31f4e-210">Another user, User 2, signs up for the subscription on October 1, 2021.</span></span> <span data-ttu-id="31f4e-211">Пользователь 2 может использовать версию Teams Exploratory в течение двух месяцев, так как дата окончания установлена на 31 декабря 2021 года, поскольку это подписка той же организации, что у Пользователя 1.</span><span class="sxs-lookup"><span data-stu-id="31f4e-211">User 2 can use Teams Exploratory for two months, as their end-date will be December 31, 2021 because they're under the same organization's subscription as User 1.</span></span>

### <a name="what-should-administrators-do-at-the-end-of-the-12-month-teams-exploratory-experience"></a><span data-ttu-id="31f4e-212">Что следует сделать администраторами по окончании 12 месяцев использования версии Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="31f4e-212">What should administrators do at the end of the 12 month Teams Exploratory experience</span></span>

<span data-ttu-id="31f4e-213">По окончании подписки на 12 месяцев администраторам следует перевести всех пользователей версии Teams Exploratory на платную лицензию, в которую входит Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="31f4e-213">At the end of the 12 month subscription, administrators should convert all Teams Exploratory users to a paid license that includes Teams.</span></span> <span data-ttu-id="31f4e-214">Это необходимо сделать до окончания действия подписки на версию Teams Exploratory, чтобы не прерывать работу пользователей.</span><span class="sxs-lookup"><span data-stu-id="31f4e-214">It is vital to ensure this is completed before the Teams Exploratory subscription expires to avoid any disruption to user's experience.</span></span>


> [!NOTE]
> <span data-ttu-id="31f4e-215">Возможность запуска клиентами новых лицензий на пробную версию Exploratory будет отключена и заблокирована в течение 3 месяцев после истечения срока действия предыдущей лицензии на пробную версию Exploratory.</span><span class="sxs-lookup"><span data-stu-id="31f4e-215">Customers will be disabled and blocked from starting a new Exploratory trial licenses for 3 months past the expiration of their previous Exploratory trial license.</span></span>

<span data-ttu-id="31f4e-216">Дополнительные сведения см. в разделе [Повышение статуса пользователей с лицензией Teams Exploratory](#upgrade-users-from-the-teams-exploratory-license)) выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="31f4e-216">For more information, see [Upgrade users from the Teams Exploratory license](#upgrade-users-from-the-teams-exploratory-license)), above in this article.</span></span>

