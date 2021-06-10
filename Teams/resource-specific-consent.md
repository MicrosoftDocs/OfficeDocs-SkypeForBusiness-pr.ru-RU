---
title: Согласие для конкретного ресурса в Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Узнайте о параметрах, которые необходимо настроить для контроля того, могут ли владельцы команд в вашей организации дать согласие на приложения.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7b9379db7760fa8ef03440c24b93cb0223b4bee
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117627"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a><span data-ttu-id="6fef1-103">Согласие для конкретного ресурса в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6fef1-103">Resource-specific consent in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="6fef1-104">Согласие на доступ к ресурсам в Microsoft Teams позволяет владельцам команд предоставить приложениям разрешение на доступ к данным группы.</span><span class="sxs-lookup"><span data-stu-id="6fef1-104">Resource-specific consent in Microsoft Teams lets team owners give consent to apps to access team data.</span></span> <span data-ttu-id="6fef1-105">Примерами такого доступа может быть возможность читать сообщения канала, создавать и удалять каналы, а также создавать и удалять вкладки каналов.</span><span class="sxs-lookup"><span data-stu-id="6fef1-105">Examples of such access include the ability to read channel messages, create and delete channels, and create and remove channel tabs.</span></span>

<span data-ttu-id="6fef1-106">Как администратор вы управляете тем, могут ли владельцы команд в вашей организации предоставить согласие с помощью параметров, настроенных с помощью модуля PowerShell Azure Active Directory (Azure AD) или портала Azure и Microsoft Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="6fef1-106">As an admin, you control whether team owners in your organization can give consent through settings that you configure by using the Azure Active Directory (Azure AD) PowerShell module or the Azure portal and the Microsoft Teams admin center.</span></span>  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a><span data-ttu-id="6fef1-107">Настройка того, могут ли владельцы команд дать согласие на приложения</span><span class="sxs-lookup"><span data-stu-id="6fef1-107">Set whether team owners can give consent to apps</span></span>

<span data-ttu-id="6fef1-108">Ниже параметров, которые необходимо настроить для контроля того, могут ли владельцы команд дать согласие на приложения.</span><span class="sxs-lookup"><span data-stu-id="6fef1-108">Here are the settings that you must set to control whether team owners can give consent to apps.</span></span> <span data-ttu-id="6fef1-109">Обязательно просмотрите все следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="6fef1-109">Be sure to review all the following settings.</span></span>

### <a name="settings-in-azure-ad"></a><span data-ttu-id="6fef1-110">Параметры Azure AD</span><span class="sxs-lookup"><span data-stu-id="6fef1-110">Settings in Azure AD</span></span>

<span data-ttu-id="6fef1-111">Следующие два параметра определяют, могут ли владельцы команд дать согласие на приложения.</span><span class="sxs-lookup"><span data-stu-id="6fef1-111">The following two settings determine whether team owners can give consent to apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fef1-112">Изменение этих параметров не влияет на доступ к данным для приложений, которые уже получили согласие.</span><span class="sxs-lookup"><span data-stu-id="6fef1-112">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="6fef1-113">Например, если вы настроили эти параметры, чтобы запретить владельцам команд предоставлять согласие, эти изменения не будут удалять уже предоставленный доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="6fef1-113">For example, if you configure these settings to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a><span data-ttu-id="6fef1-114">Параметр "Пользователи могут согласиться на доступ приложений к данным компании от своего имени"</span><span class="sxs-lookup"><span data-stu-id="6fef1-114">The "Users can consent to apps accessing company data on their behalf" setting</span></span>

<span data-ttu-id="6fef1-115">Этот параметр позволяет контролировать, могут ли пользователи в вашей организации согласиться на доступ к приложениям от их имени.</span><span class="sxs-lookup"><span data-stu-id="6fef1-115">This setting controls whether users in your organization can consent to apps on their behalf.</span></span> <span data-ttu-id="6fef1-116">Чтобы владельцы команд могли дать согласие, этот параметр должен быть установлен на **Да.**</span><span class="sxs-lookup"><span data-stu-id="6fef1-116">To enable team owners to give consent, this setting must be set to **Yes**.</span></span> <span data-ttu-id="6fef1-117">Чтобы управлять этим параметром, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="6fef1-117">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="6fef1-118">На портале Azure перейдите к Enterprise **приложениям**  >  **Пользовательские параметры**.</span><span class="sxs-lookup"><span data-stu-id="6fef1-118">In the Azure portal, go to **Enterprise applications** > **User settings**.</span></span>
2. <span data-ttu-id="6fef1-119">В **Enterprise приложений** установите для  приложений разрешение Пользователи могут соглашаться на доступ к приложениям, которые имеют доступ к данным компании от их имени, **на "Нет"** или **"Да".**</span><span class="sxs-lookup"><span data-stu-id="6fef1-119">Under **Enterprise applications**, set **Users can consent to apps accessing company data on their behalf** to **No** or **Yes**.</span></span>

<span data-ttu-id="6fef1-120">Вы также можете управлять этим параметром с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fef1-120">You can also manage this setting using PowerShell.</span></span> <span data-ttu-id="6fef1-121">Дополнительные данные см. [в этой записи.](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)</span><span class="sxs-lookup"><span data-stu-id="6fef1-121">To learn more, see [Configure user content to applications](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).</span></span>

#### <a name="the-enablegroupspecificconsent-setting"></a><span data-ttu-id="6fef1-122">Параметр EnableGroupSpecificConsent</span><span class="sxs-lookup"><span data-stu-id="6fef1-122">The "EnableGroupSpecificConsent" setting</span></span>

<span data-ttu-id="6fef1-123">Этот параметр контролирует, могут ли пользователи в вашей организации согласиться на доступ приложений к данным компании для своих групп.</span><span class="sxs-lookup"><span data-stu-id="6fef1-123">This setting controls whether users in your organization can consent to apps accessing company data for the groups that they own.</span></span> <span data-ttu-id="6fef1-124">Этот параметр должен быть включен для владельцев команд, чтобы дать согласие.</span><span class="sxs-lookup"><span data-stu-id="6fef1-124">This setting must be enabled for team owners to give consent.</span></span> <span data-ttu-id="6fef1-125">Сведения о том, как управлять этим параметром с помощью PowerShell, см. в сведениях о том, как настроить согласие владельца группы на доступ к данным [группы.](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)</span><span class="sxs-lookup"><span data-stu-id="6fef1-125">For steps on how to manage this setting by using PowerShell, see [Configure group owner consent to apps accessing group data](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).</span></span>

### <a name="settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="6fef1-126">Параметры в Центре Microsoft Teams администрирования</span><span class="sxs-lookup"><span data-stu-id="6fef1-126">Settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="6fef1-127">Помимо параметров в Azure AD, параметры приложений [](manage-apps.md) для всей организации на странице Управление приложениями определяют, заблокировано [](teams-app-permission-policies.md) ли приложение или разрешено на странице Управление приложениями, а политика разрешений приложения, назначенная владельцу группы, определяет, может ли владелец группы предоставить согласие. [](manage-apps.md#manage-org-wide-app-settings) [](manage-apps.md#allow-and-block-apps)</span><span class="sxs-lookup"><span data-stu-id="6fef1-127">In addition to settings in Azure AD, [org-wide app settings](manage-apps.md#manage-org-wide-app-settings) on the [Manage apps](manage-apps.md) page, whether an app is blocked or allowed on the [Manage apps](manage-apps.md#allow-and-block-apps) page, and the [app permission policy](teams-app-permission-policies.md) assigned to the team owner determine whether a team owner can give consent.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fef1-128">Изменение этих параметров не влияет на доступ к данным для приложений, которые уже получили согласие.</span><span class="sxs-lookup"><span data-stu-id="6fef1-128">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="6fef1-129">Например, если вы отключили сторонние приложения на всей организации или заблокировали определенные приложения, чтобы запретить владельцам команд предоставлять согласие, эти изменения не удаляют уже предоставленный доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="6fef1-129">For example, if you disable third-party apps org-wide or if you block specific apps to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a><span data-ttu-id="6fef1-130">Параметр "Разрешить приложения сторонних разработчиков" в параметрах приложений для всей организации</span><span class="sxs-lookup"><span data-stu-id="6fef1-130">The "Allow third party apps" setting in org-wide app settings</span></span>

<span data-ttu-id="6fef1-131">Этот параметр приложения для всей организации контролирует возможность использования сторонних приложений пользователями в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="6fef1-131">This org-wide app setting controls whether users in your organization can use third-party apps.</span></span> <span data-ttu-id="6fef1-132">Этот параметр должен быть включиться, чтобы владельцы команд могли дать согласие.</span><span class="sxs-lookup"><span data-stu-id="6fef1-132">This setting must be on to enable team owners to give consent.</span></span> <span data-ttu-id="6fef1-133">Чтобы управлять этим параметром, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="6fef1-133">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="6fef1-134">В левой области навигации Центра администрирования Microsoft Teams перейдите в Teams **приложения** Управление приложениями , а затем щелкните Параметры приложений  >  для **всей организации.**</span><span class="sxs-lookup"><span data-stu-id="6fef1-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
2. <span data-ttu-id="6fef1-135">В **области Сторонние приложения** отключите или включите разрешение **сторонних приложений**.</span><span class="sxs-lookup"><span data-stu-id="6fef1-135">Under **Third party apps**, turn off or turn on **Allow third party apps**.</span></span>

    ![Снимок экрана: параметр "Разрешить приложения сторонних Teams"](media/resource-specific-consent-org-wide-setting.png)

<span data-ttu-id="6fef1-137">Чтобы изменения вступили в силу, может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="6fef1-137">You may have to wait up to 24 hours for your changes to take effect.</span></span>

#### <a name="allow-or-block-the-app-at-the-org-level"></a><span data-ttu-id="6fef1-138">Разрешение или блокировка приложения на уровне организации</span><span class="sxs-lookup"><span data-stu-id="6fef1-138">Allow or block the app at the org level</span></span>

<span data-ttu-id="6fef1-139">Когда вы блокируете или [](manage-apps.md#allow-and-block-apps) разрешаете приложение на странице Управление приложениями, это приложение блокируется или разрешено для всех пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="6fef1-139">When you block or allow an app on the [Manage apps](manage-apps.md#allow-and-block-apps) page, that app is blocked or allowed for all users in your organization.</span></span> <span data-ttu-id="6fef1-140">Владельцы команд могут дать согласие на приложение только в том случае, если это разрешено.</span><span class="sxs-lookup"><span data-stu-id="6fef1-140">Team owners can only give consent to an app if the app is allowed.</span></span> <span data-ttu-id="6fef1-141">Чтобы разрешить или заблокировать приложение на уровне организации, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="6fef1-141">To allow or block an app at the org level, do the following:</span></span>

1. <span data-ttu-id="6fef1-142">В левой панели навигации Центра администрирования Microsoft Teams выберите **Приложения Teams** > **Управление приложениями**.</span><span class="sxs-lookup"><span data-stu-id="6fef1-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="6fef1-143">На странице Управление приложениями выберите приложение  и нажмите кнопку Заблокировать, чтобы заблокировать его, или **разрешить.**</span><span class="sxs-lookup"><span data-stu-id="6fef1-143">On the Manage apps page, select the app, and then click **Block** to block it or click **Allow** to allow it.</span></span>

    ![Снимок экрана: заблокированные приложения в настройках для всей организации](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a><span data-ttu-id="6fef1-145">Политика разрешений приложения, назначенная владельцу группы</span><span class="sxs-lookup"><span data-stu-id="6fef1-145">App permission policy assigned to the team owner</span></span>

<span data-ttu-id="6fef1-146">Владельцы команд могут дать согласие только приложениям, которые их политика разрешений разрешает им запускать.</span><span class="sxs-lookup"><span data-stu-id="6fef1-146">Team owners can only give consent to apps that their app permission policy allows them to run.</span></span> <span data-ttu-id="6fef1-147">Чтобы просмотреть политику разрешений приложения, назначенную владельцу группы, и управлять ее политиками, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="6fef1-147">To view and manage the app permission policy that's assigned to a team owner, do the following:</span></span>

1. <span data-ttu-id="6fef1-148">В левой области навигации центра администрирования Microsoft Teams перейдите в меню **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="6fef1-148">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="6fef1-149">Дважды щелкните отображаемую имя владельца команды и выберите **команду Политики.**</span><span class="sxs-lookup"><span data-stu-id="6fef1-149">Double-click the display name of the team owner, and then click **Policies**.</span></span>
3. <span data-ttu-id="6fef1-150">Политика, назначенная владельцу группы, указана в списке **Политика разрешений приложений.**</span><span class="sxs-lookup"><span data-stu-id="6fef1-150">The policy assigned to the team owner is listed under **App permission policy**.</span></span>
    - <span data-ttu-id="6fef1-151">Чтобы назначить другую политику, нажмите кнопку **Изменить** и выберите политику, которую вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="6fef1-151">To assign a different policy, click **Edit**, and then select the policy that you want to assign.</span></span>
    - <span data-ttu-id="6fef1-152">Чтобы изменить параметры политики, назначенной владельцу группы, щелкните ее имя и внести нужные изменения.</span><span class="sxs-lookup"><span data-stu-id="6fef1-152">To edit the settings of the policy that's assigned to the team owner, click the policy name, and then make the changes that you want.</span></span>  

## <a name="uploading-custom-apps"></a><span data-ttu-id="6fef1-153">Отправка пользовательских приложений</span><span class="sxs-lookup"><span data-stu-id="6fef1-153">Uploading custom apps</span></span>

<span data-ttu-id="6fef1-154">При отправке настраиваемого приложения (также известной боковой загрузки), которое использует согласие для конкретного ресурса, оно должно быть получено от клиента, в который оно устанавливается.</span><span class="sxs-lookup"><span data-stu-id="6fef1-154">When uploading a custom app (also known sideloading) that uses resource-specific consent, the app must come from the tenant that it's being installed to.</span></span> <span data-ttu-id="6fef1-155">Другими словами, регистрация приложения Azure AD должна быть зарегистрирована в этом клиенте.</span><span class="sxs-lookup"><span data-stu-id="6fef1-155">In other words, the Azure AD app registration must be from this tenant.</span></span> <span data-ttu-id="6fef1-156">Это ограничение не распространяется на глобальных администраторов, и они могут загружать пользовательские приложения из любого клиента непосредственно в группу (загрузку на стороне) или в каталог приложений клиента.</span><span class="sxs-lookup"><span data-stu-id="6fef1-156">Global admins are exempted from this restriction, and can upload custom apps from any tenant, either directly to a team (sideloading) or to the tenant app catalog.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6fef1-157">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="6fef1-157">Related topics</span></span>

- [<span data-ttu-id="6fef1-158">Доступные разрешения RSC</span><span class="sxs-lookup"><span data-stu-id="6fef1-158">Available RSC permissions</span></span>](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [<span data-ttu-id="6fef1-159">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="6fef1-159">Microsoft Graph</span></span>](https://developer.microsoft.com/graph)
- [<span data-ttu-id="6fef1-160">Управление приложениями в Центре Microsoft Teams администрирования</span><span class="sxs-lookup"><span data-stu-id="6fef1-160">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="6fef1-161">Управление политиками разрешений для приложений в Teams</span><span class="sxs-lookup"><span data-stu-id="6fef1-161">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)