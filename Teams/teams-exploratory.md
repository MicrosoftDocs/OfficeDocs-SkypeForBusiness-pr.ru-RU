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
ms.openlocfilehash: f27dc7e8772e25b6dcc91622cabec421e058af7b
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031485"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="62aa2-103">Управление лицензией на Microsoft Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="62aa2-103">Manage the Microsoft Teams Exploratory license</span></span>
=======================================================

<span data-ttu-id="62aa2-p101">Предложение Microsoft Teams Exploratory позволяет пользователям в вашей организации, у которых есть лицензия на Azure Active Directory (Azure AD), но нет лицензии на Teams, оформить ознакомительную лицензию на Teams. Администраторы могут включать и отключать эту функцию для пользователей в организации. Предыдущая [пробная версия Microsoft Commercial Cloud](iw-trial-teams.md) теперь заменена предложением Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="62aa2-p101">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (Azure AD) and aren't licensed for Teams initiate an exploratory experience of Teams. Admins can switch this feature on or off for users in their organization. The earlier [Microsoft Commercial Cloud Trial](iw-trial-teams.md) is now replaced by The Teams Exploratory experience.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="62aa2-107">Что включает предложение Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="62aa2-107">What's in the Teams Exploratory experience</span></span>

<span data-ttu-id="62aa2-108">Администратору будут представлены следующие планы обслуживания, входящие в предложение Teams Exploratory:</span><span class="sxs-lookup"><span data-stu-id="62aa2-108">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>

- <span data-ttu-id="62aa2-109">Exchange Online (план 1)</span><span class="sxs-lookup"><span data-stu-id="62aa2-109">Exchange Online (Plan 1)</span></span>
- <span data-ttu-id="62aa2-110">Flow для Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="62aa2-110">Flow for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="62aa2-111">MyAnalytics для анализа данных</span><span class="sxs-lookup"><span data-stu-id="62aa2-111">Insights by MyAnalytics</span></span>
- <span data-ttu-id="62aa2-112">Microsoft Forms (план E1)</span><span class="sxs-lookup"><span data-stu-id="62aa2-112">Microsoft Forms (Plan E1)</span></span>
- <span data-ttu-id="62aa2-113">Планировщик (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="62aa2-113">Microsoft Planner</span></span>
- <span data-ttu-id="62aa2-114">Поиск (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="62aa2-114">Microsoft Search</span></span>
- <span data-ttu-id="62aa2-115">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="62aa2-115">Microsoft StaffHub</span></span>
- <span data-ttu-id="62aa2-116">Microsoft Stream для SKU Microsoft 365 и Office 365 E1 <sup>1</1></span><span class="sxs-lookup"><span data-stu-id="62aa2-116">Microsoft Stream for Microsoft 365 and Office 365 E1 SKUs <sup>1</1></span></span>
- <span data-ttu-id="62aa2-117">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="62aa2-117">Microsoft Teams</span></span>
- <span data-ttu-id="62aa2-118">Управление мобильными устройствами для Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="62aa2-118">Mobile Device Management for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="62aa2-119">Приложения Office Mobile для Office 365</span><span class="sxs-lookup"><span data-stu-id="62aa2-119">Office Mobile Apps for Office 365</span></span>
- <span data-ttu-id="62aa2-120">Office Online</span><span class="sxs-lookup"><span data-stu-id="62aa2-120">Office Online</span></span>
- <span data-ttu-id="62aa2-121">PowerApps для Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="62aa2-121">PowerApps for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="62aa2-122">SharePoint Online (план 1)</span><span class="sxs-lookup"><span data-stu-id="62aa2-122">SharePoint Online (Plan 1)</span></span>
- <span data-ttu-id="62aa2-123">Sway</span><span class="sxs-lookup"><span data-stu-id="62aa2-123">Sway</span></span>
- <span data-ttu-id="62aa2-124">To-Do (план 1)</span><span class="sxs-lookup"><span data-stu-id="62aa2-124">To-Do (Plan 1)</span></span>
- <span data-ttu-id="62aa2-125">Доска (план 1)</span><span class="sxs-lookup"><span data-stu-id="62aa2-125">Whiteboard (Plan 1)</span></span>
- <span data-ttu-id="62aa2-126">Yammer корпоративный</span><span class="sxs-lookup"><span data-stu-id="62aa2-126">Yammer Enterprise</span></span>

  <span data-ttu-id="62aa2-p102"><sup>1</sup> Переход от использования Microsoft Stream к [OneDrive для бизнеса и SharePoint для записи собраний](tmr-meeting-recording-change.md) будет поэтапным. При запуске вы сможете согласиться на использование этого интерфейса. В ноябре потребуется отказаться от использования, если вы хотите продолжить использование Stream. В начале 2021 года мы сделаем использование OneDrive для бизнеса и SharePoint для новых записей собраний обязательным для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="62aa2-p102"><sup>1</sup> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt in to this experience. In November, you'll have to opt out if you want to continue using Stream. Sometime in early 2021, we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

## <a name="whos-eligible"></a><span data-ttu-id="62aa2-131">Кто имеет право на использование</span><span class="sxs-lookup"><span data-stu-id="62aa2-131">Who's eligible</span></span>

<span data-ttu-id="62aa2-132">Пользователи соответствуют критериям Teams Exploratory, если они:</span><span class="sxs-lookup"><span data-stu-id="62aa2-132">Users fit the criteria for a Teams Exploratory experience if they:</span></span>

- <span data-ttu-id="62aa2-133">Имеют адрес электронной почты с управляемым доменом Azure AD.</span><span class="sxs-lookup"><span data-stu-id="62aa2-133">Have a managed Azure AD domain email address.</span></span>
- <span data-ttu-id="62aa2-134">Входят в состав клиента с платной подпиской.</span><span class="sxs-lookup"><span data-stu-id="62aa2-134">Belong to a tenant with a paid subscription.</span></span>

<span data-ttu-id="62aa2-p103">У пользователей есть возможность зарегистрироваться для получения приложений и пробных версий (в Центре администрирования Microsoft 365). Дополнительные сведения см. в разделе [Управление предложением Teams Exploratory](#manage-the-teams-exploratory-experience) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="62aa2-p103">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center). For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span>

## <a name="who-isnt-eligible"></a><span data-ttu-id="62aa2-137">Кто не имеет права на использование</span><span class="sxs-lookup"><span data-stu-id="62aa2-137">Who isn't eligible</span></span>

<span data-ttu-id="62aa2-138">Пользователи не соответствуют критериям, если они:</span><span class="sxs-lookup"><span data-stu-id="62aa2-138">Users don't fit the criteria if they:</span></span>

- <span data-ttu-id="62aa2-139">Имеют или ранее имели платную, бесплатную или пробную лицензию на Teams.</span><span class="sxs-lookup"><span data-stu-id="62aa2-139">Currently or previously had Teams from a paid, unpaid or trial license</span></span> 
- <span data-ttu-id="62aa2-140">Входят в состав клиента, который использовал/получил по крайней мере одно специальное предложение, связанное с COVID.</span><span class="sxs-lookup"><span data-stu-id="62aa2-140">Are in a tenant that used/received at least one special COVID offer.</span></span>

<span data-ttu-id="62aa2-141">Ваша организация не может использовать это предложение, если вы являетесь клиентом партнера по синдикации или клиентом GCC, GCC High, DoD либо EDU.</span><span class="sxs-lookup"><span data-stu-id="62aa2-141">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="62aa2-142">Регистрация для получения Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="62aa2-142">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="62aa2-p104">Пользователи, имеющие право на использование, могут зарегистрироваться для получения предложения Teams Exploratory, выполнив вход в Teams ([teams.microsoft.com](https://teams.microsoft.com)). Им будет автоматически назначена лицензия, и администратор клиента получит соответствующее уведомление по электронной почте, когда пользователь в организации впервые приступит к работе с Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="62aa2-p104">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams ([teams.microsoft.com](https://teams.microsoft.com)). They'll be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="62aa2-145">Управление предложением Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="62aa2-145">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="62aa2-146">Предложение Teams Exploratory предназначено для активации отдельными пользователями, и вы не можете активировать его от имени сотрудников, являющихся конечными пользователями.</span><span class="sxs-lookup"><span data-stu-id="62aa2-146">The Teams Exploratory experience is meant to be initiated by individual end users, and you can't initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="62aa2-p105">Предложение Teams Exploratory включает лицензию на Exchange Online, но она должна быть назначена пользователю администратором. Если у пользователя нет лицензии на Exchange, а администратор еще не назначил лицензию на Exchange Online, пользователь не сможет планировать собрания в Teams и использовать другие функции Teams.</span><span class="sxs-lookup"><span data-stu-id="62aa2-p105">The Teams Exploratory experience comes with an Exchange Online license, but it won't be assigned to the user until the admin assigns it. If the user doesn't have an Exchange license already, and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and might be missing other Teams functionality.</span></span>

<span data-ttu-id="62aa2-149">Администраторы могут отключить возможность использования Teams Exploratory для пользователей в своей организации с помощью переключателя **Пробные версии приложений и служб**.</span><span class="sxs-lookup"><span data-stu-id="62aa2-149">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>

### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="62aa2-150">Запрет на установку пользователями пробных версий приложений и служб</span><span class="sxs-lookup"><span data-stu-id="62aa2-150">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="62aa2-151">Вы можете отключить возможность установки пробных версий приложений и служб, чтобы пользователи не могли использовать Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="62aa2-151">You can turn off a user's ability to install trial apps and services, which would prevent the user from running the Teams Exploratory experience.</span></span>

1. <span data-ttu-id="62aa2-152">В Центре администрирования Microsoft 365 выберите **Параметры** > **Параметры организации** , щелкните **Службы** и нажмите **Приложения и службы, лицензированные для отдельных пользователей**.</span><span class="sxs-lookup"><span data-stu-id="62aa2-152">From the Microsoft 365 admin center, go to **Settings** > **Org settings** , select **Services** , and then select **User owned apps and services**.</span></span>

    ![страница "Службы" в Центре администрирования](media/iw-trial-services.png)

2. <span data-ttu-id="62aa2-154">Снимите флажок **Разрешить пользователям устанавливать пробные версии приложений и служб**.</span><span class="sxs-lookup"><span data-stu-id="62aa2-154">Clear the **Let users install trial apps and services** check box.</span></span>

    ![страница "Приложения и службы, лицензированные для отдельных пользователей" в Центре администрирования](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="62aa2-156">Если ваша организация не имеет права на использование Teams Exploratory, параметр **Разрешить пользователям устанавливать пробные версии приложений и служб** будет отсутствовать.</span><span class="sxs-lookup"><span data-stu-id="62aa2-156">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="62aa2-157">Управление доступностью для пользователя с лицензией, включающей Teams</span><span class="sxs-lookup"><span data-stu-id="62aa2-157">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="62aa2-p106">Пользователь, которому назначена лицензия, включающая Teams, не имеет права на использование Teams Exploratory. Если план обслуживания Teams включен, пользователь может выполнить вход в систему и использовать Teams. Если план обслуживания отключен, пользователь не может выполнить вход в систему и возможности Teams Exploratory ему недоступны. У вас должны быть права администратора.</span><span class="sxs-lookup"><span data-stu-id="62aa2-p106">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience. When the Teams service plan is turned on, the user can sign in and use Teams. If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available. You must have admin privileges.</span></span>

<span data-ttu-id="62aa2-162">Отключение доступа к Teams:</span><span class="sxs-lookup"><span data-stu-id="62aa2-162">To turn off access to Teams:</span></span>

1. <span data-ttu-id="62aa2-163">В Центре администрирования Microsoft 365 выберите **Пользователи** > **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="62aa2-163">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="62aa2-164">Установите флажок рядом с именем пользователя.</span><span class="sxs-lookup"><span data-stu-id="62aa2-164">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="62aa2-165">В правой части строки **Лицензии на продукты** щелкните ссылку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="62aa2-165">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="62aa2-166">В области **Лицензии на продукты** установите переключатель в положение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="62aa2-166">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![страница "Лицензии на продукты" в Центре администрирования.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="62aa2-168">Управление доступностью Teams для пользователей, уже использующих Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="62aa2-168">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="62aa2-p107">Если пользователь использует предложение Teams Exploratory, вы можете отключить его, удалив лицензию или план обслуживания. У вас должны быть права администратора.</span><span class="sxs-lookup"><span data-stu-id="62aa2-p107">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan. You must have admin privileges.</span></span>

<span data-ttu-id="62aa2-171">Чтобы отключить лицензию на Teams Exploratory, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="62aa2-171">To turn off the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="62aa2-172">В Центре администрирования Microsoft 365 выберите **Пользователи** > **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="62aa2-172">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="62aa2-173">Установите флажок рядом с именем пользователя.</span><span class="sxs-lookup"><span data-stu-id="62aa2-173">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="62aa2-174">В правой части строки **Лицензии на продукты** щелкните ссылку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="62aa2-174">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="62aa2-175">В области **Лицензии на продукты** установите переключатель для лицензии на это предложение в положение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="62aa2-175">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off**.</span></span>

    >[!Note]
    ><span data-ttu-id="62aa2-176">Переключатель для Teams Exploratory отобразится после того, как первый пользователь в организации запустит это предложение.</span><span class="sxs-lookup"><span data-stu-id="62aa2-176">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="62aa2-177">Управление Teams для пользователей с лицензией на Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="62aa2-177">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="62aa2-p108">Управление пользователями, у которых есть лицензия Teams Exploratory, аналогично управлению пользователями с обычной платной лицензией. Дополнительные сведения см. в разделе [Управление параметрами Teams в организации](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="62aa2-p108">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license. For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-the-teams-exploratory-license"></a><span data-ttu-id="62aa2-180">Перевод пользователей с лицензии Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="62aa2-180">Upgrade users from the Teams Exploratory license</span></span>

<span data-ttu-id="62aa2-181">Чтобы перевести пользователей с лицензии Teams Exploratory (у вас должны быть права администратора), выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="62aa2-181">To upgrade users from the Teams Exploratory license (you must have admin privileges), do the following tasks:</span></span>

1. <span data-ttu-id="62aa2-182">Приобретите подписку, в которую входит Teams.</span><span class="sxs-lookup"><span data-stu-id="62aa2-182">Purchase a subscription that includes Teams.</span></span>

2. <span data-ttu-id="62aa2-183">Удалите подписку пользователя на Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="62aa2-183">Remove the Teams Exploratory subscription from the user.</span></span>

3. <span data-ttu-id="62aa2-184">Назначьте приобретенную лицензию.</span><span class="sxs-lookup"><span data-stu-id="62aa2-184">Assign the newly purchased license.</span></span>

<span data-ttu-id="62aa2-185">Для получения дополнительной информации см. [Описание службы Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="62aa2-185">For more information, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

> [!NOTE]
> <span data-ttu-id="62aa2-p109">Если срок действия лицензии на Teams Exploratory закончится и пользователь сразу не перейдет на подписку, включающую Teams, у пользователя будет 30 дней льготного периода, а затем еще 30 дней, после чего данные будут удалены. Пользователь по-прежнему будет существовать в Azure Active Directory. После того, как пользователю будет назначена новая лицензия для повторного включения функций Teams, содержимое будет по-прежнему существовать, если пользователь будет добавлен в течение льготного периода.</span><span class="sxs-lookup"><span data-stu-id="62aa2-p109">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, they have 30 days of grace period and then another 30 days after which time the data is going to be deleted. The user still exists in Azure Active Directory. Once a new license is assigned to the user to enable Teams functionality again, all content will still exist if the user is added within the grace period time frame.</span></span>

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a><span data-ttu-id="62aa2-189">Что произойдет с устаревшими лицензиями на Microsoft Teams Commercial Cloud Trial</span><span class="sxs-lookup"><span data-stu-id="62aa2-189">What happens to legacy Microsoft Teams Commercial Cloud Trial licenses</span></span>

<span data-ttu-id="62aa2-p110">С февраля 2020 г. соответствующие критериям пользователи могут начать работу с последней версией Microsoft Teams Exploratory. Все устаревшие лицензии на Teams Commercial Cloud Trial будут автоматически преобразованы в лицензии на новое предложение до истечения срока действия пробной версии.</span><span class="sxs-lookup"><span data-stu-id="62aa2-p110">As of February 2020, eligible users can begin using the latest Microsoft Teams Exploratory experience. All legacy Teams Commercial Cloud Trial licenses will be automatically converted to the new offer before their trial expires.</span></span>

<span data-ttu-id="62aa2-p111">При первом входе пользователя в Teams Commercial Cloud Trial с истекшим сроком действия этому пользователю автоматически назначается лицензия на использование Teams Exploratory. Конвертация не происходит, пока пользователь не выполнит вход в систему.</span><span class="sxs-lookup"><span data-stu-id="62aa2-p111">When users sign in to their expired Teams Commercial Cloud Trial for the first time, we automatically assign a Teams Exploratory experience license to those users. Users aren't converted until they sign in.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="62aa2-194">Удаление лицензии на Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="62aa2-194">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="62aa2-195">Если вы хотите удалить эту лицензию с помощью PowerShell, см. статью [Использование PowerShell в Office 365 для удаления лицензий из учетных записей пользователей](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="62aa2-195">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="62aa2-196">Если вы хотите удалить эту лицензию на портале администрирования, см. статью [Удаление пользователя из организации](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span><span class="sxs-lookup"><span data-stu-id="62aa2-196">If you would like to remove this license through the admin portal, see: [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span></span>

## <a name="what-is-the-data-retention-policy"></a><span data-ttu-id="62aa2-197">Что такое политика хранения данных</span><span class="sxs-lookup"><span data-stu-id="62aa2-197">What is the data retention policy</span></span>

<span data-ttu-id="62aa2-198">См. [Сведения о подписке на Microsoft 365](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="62aa2-198">See [Microsoft 365 subscription information](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="62aa2-199">Срок действия предложения Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="62aa2-199">How long does the Teams Exploratory experience last</span></span>

<span data-ttu-id="62aa2-p112">Предложение Microsoft Teams Exploratory действует без дополнительной платы до наступления следующей **годовщины заключения вашего соглашения** или до его **продления** в январе 2021 г. или позже. В это время пользователям, имеющим лицензию на Microsoft Exploratory, нужно будет перейти на платную лицензию, включающую Teams. Все лицензии Microsoft Exploratory, оформленные после этого, будут действовать без дополнительной платы до наступления следующей **годовщины со дня заключения соглашения** или цикла **продления**.</span><span class="sxs-lookup"><span data-stu-id="62aa2-p112">The Microsoft Teams Exploratory experience is available at no additional cost until your next **agreement anniversary** or **renewal** on or after January 2021. At that time, end users on a Microsoft Exploratory experience license will need to move to a paid license that includes Teams. Any Microsoft Exploratory experience licenses initiated after that will remain available at no additional cost until your next **anniversary** or **renewal** cycle.</span></span>

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-the-anniversary-or-renewal-date"></a><span data-ttu-id="62aa2-203">Что произойдет, если пользователь оформит лицензию Microsoft Teams Exploratory непосредственно перед истечением очередного года со дня заключения моего соглашения или перед его продлением</span><span class="sxs-lookup"><span data-stu-id="62aa2-203">What happens if an end user initiates the Microsoft Teams Exploratory experience just before the anniversary or renewal date</span></span>

<span data-ttu-id="62aa2-204">Для лицензий Microsoft Teams Exploratory, оформленных менее чем за 90 дней до наступления следующей **годовщины заключения вашего соглашения** или его **продления** , не потребуется переход на платную лицензию до следующей годовщины заключения соглашения или его следующего продления.</span><span class="sxs-lookup"><span data-stu-id="62aa2-204">Microsoft Teams Exploratory experience licenses initiated within 90 days of your **agreement anniversary** or **renewal** won't be required to move to a paid license until the subsequent anniversary or renewal cycle.</span></span>

### <a name="what-if-my-agreement-doesnt-have-an-anniversary-or-yearly-renewal-date-for-example-month-to-month-agreements"></a><span data-ttu-id="62aa2-205">Что если в моем соглашении отсутствует годовщина заключения или ежегодная дата возобновления (например, ежемесячные соглашения)</span><span class="sxs-lookup"><span data-stu-id="62aa2-205">What if my agreement doesn’t have an anniversary or yearly renewal date (for example, month-to-month agreements)</span></span>

<span data-ttu-id="62aa2-p113">Для соглашений без годовщины или ежегодной даты возобновления последующий год после активации первым пользователем лицензий Microsoft Teams Exploratory будет считаться годовщиной или датой возобновления. Пользователи с лицензиями на Microsoft Teams Exploratory должны быть переведены на платную лицензию к этой дате каждого года согласно политикам, описанным выше.</span><span class="sxs-lookup"><span data-stu-id="62aa2-p113">For agreements without an anniversary or yearly renewal date, the subsequent year after the first end-user activates the Microsoft Teams Exploratory experience licenses will be treated as the anniversary or renewal date. Users on the Microsoft Teams Exploratory license must be converted to a paid license by that date each year, according to the policies outlined in this article.</span></span>

<span data-ttu-id="62aa2-208">Например, если первый пользователь активирует Microsoft Teams Exploratory 19 июня 2020 г., он и все другие соответствующие пользователи в клиенте должны быть переведены на платную лицензию Teams до 19 июня 2021 г.</span><span class="sxs-lookup"><span data-stu-id="62aa2-208">For example, if the first end user activates Microsoft Teams Exploratory on June 19, 2020, then they and all other eligible users in the customer tenant must convert to a paid license with Teams by June 19, 2021.</span></span>

> [!Note]
> <span data-ttu-id="62aa2-209">Возможность запуска клиентами новых лицензий на пробную версию Exploratory будет отключена и заблокирована в течение 3 месяцев после истечения срока действия предыдущей лицензии на пробную версию Exploratory.</span><span class="sxs-lookup"><span data-stu-id="62aa2-209">Customers will be disabled and blocked from starting a new Exploratory trial licenses for 3 months past the expiration of their previous Exploratory trial license.</span></span>
