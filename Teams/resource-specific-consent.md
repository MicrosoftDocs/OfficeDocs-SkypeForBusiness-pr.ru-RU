---
title: Согласие для конкретных ресурсов в Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Узнайте о параметрах, которые необходимо настроить, чтобы контролировать, могут ли владельцы команд в вашей организации давать согласие на приложения.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1ed13f1f85b0c7eccead3737c4549931f016284c
ms.sourcegitcommit: 682566e51a9e5f0fc65540535c7dcdcbd38e04c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "45429381"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a><span data-ttu-id="6436b-103">Согласие для конкретных ресурсов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6436b-103">Resource-specific consent in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="6436b-104">С помощью определенного ресурса в Microsoft Teams владельцы команд могут предоставить приложениям согласие на доступ к данным группы.</span><span class="sxs-lookup"><span data-stu-id="6436b-104">Resource-specific consent in Microsoft Teams lets team owners give consent to apps to access team data.</span></span> <span data-ttu-id="6436b-105">Примеры таких возможностей доступа: возможность читать сообщения канала, создавать и удалять каналы, а также создавать и удалять вкладки каналов.</span><span class="sxs-lookup"><span data-stu-id="6436b-105">Examples of such access include the ability to read channel messages, create and delete channels, and create and remove channel tabs.</span></span>

<span data-ttu-id="6436b-106">Как администратор вы управляете тем, могут ли владельцы команд в вашей организации предоставить согласие с помощью параметров, настроенных с помощью модуля Azure Active Directory PowerShell или портала Azure и Центра администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6436b-106">As an admin, you control whether team owners in your organization can give consent through settings that you configure by using the Azure Active Directory (Azure AD) PowerShell module or the Azure portal and the Microsoft Teams admin center.</span></span>  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a><span data-ttu-id="6436b-107">Настройка разрешения на разрешение владельцев команд на приложения</span><span class="sxs-lookup"><span data-stu-id="6436b-107">Set whether team owners can give consent to apps</span></span>

<span data-ttu-id="6436b-108">Ниже параметров, которые необходимо установить, чтобы контролировать, могут ли владельцы команд давать согласие на приложения.</span><span class="sxs-lookup"><span data-stu-id="6436b-108">Here are the settings that you must set to control whether team owners can give consent to apps.</span></span> <span data-ttu-id="6436b-109">Обязательно просмотрите все следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="6436b-109">Be sure to review all the following settings.</span></span>

### <a name="settings-in-azure-ad"></a><span data-ttu-id="6436b-110">Параметры в Azure AD</span><span class="sxs-lookup"><span data-stu-id="6436b-110">Settings in Azure AD</span></span>

<span data-ttu-id="6436b-111">Следующие два параметра определяют, смогут ли владельцы команд предоставить согласие на приложения.</span><span class="sxs-lookup"><span data-stu-id="6436b-111">The following two settings determine whether team owners can give consent to apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6436b-112">Изменение этих параметров не влияет на доступ к данным для приложений, которые уже получили согласие.</span><span class="sxs-lookup"><span data-stu-id="6436b-112">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="6436b-113">Например, если вы настроите эти параметры, чтобы владельцы команд не предоставили согласие, эти изменения не будут удалять уже предоставленный доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="6436b-113">For example, if you configure these settings to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a><span data-ttu-id="6436b-114">Параметр "Пользователи могут соглашаться на доступ приложений к данным компании от своего имени"</span><span class="sxs-lookup"><span data-stu-id="6436b-114">The "Users can consent to apps accessing company data on their behalf" setting</span></span>

<span data-ttu-id="6436b-115">Этот параметр позволяет контролировать, могут ли пользователи в вашей организации соглашаться на доступ к приложениям от их имени.</span><span class="sxs-lookup"><span data-stu-id="6436b-115">This setting controls whether users in your organization can consent to apps on their behalf.</span></span> <span data-ttu-id="6436b-116">Чтобы владельцы команд могли дать согласие, необходимо установить для этого параметра ответ **"Да".**</span><span class="sxs-lookup"><span data-stu-id="6436b-116">To enable team owners to give consent, this setting must be set to **Yes**.</span></span> <span data-ttu-id="6436b-117">Чтобы управлять этим параметром, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="6436b-117">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="6436b-118">На портале Azure перейдите в **параметры** пользователя  >  **корпоративных приложений.**</span><span class="sxs-lookup"><span data-stu-id="6436b-118">In the Azure portal, go to **Enterprise applications** > **User settings**.</span></span>
2. <span data-ttu-id="6436b-119">В **области "Корпоративные приложения"** установите для приложений, которые могут получать доступ к данным компании **от** своего имени, с разрешением **"Нет"** или **"Да".**</span><span class="sxs-lookup"><span data-stu-id="6436b-119">Under **Enterprise applications**, set **Users can consent to apps accessing company data on their behalf** to **No** or **Yes**.</span></span>

<span data-ttu-id="6436b-120">Вы также можете управлять этим параметром с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6436b-120">You can also manage this setting using PowerShell.</span></span> <span data-ttu-id="6436b-121">Дополнительные данные см. в [теме "Настройка содержимого пользователя в приложениях".](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)</span><span class="sxs-lookup"><span data-stu-id="6436b-121">To learn more, see [Configure user content to applications](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).</span></span>

#### <a name="the-enablegroupspecificconsent-setting"></a><span data-ttu-id="6436b-122">Параметр EnableGroupSpecificConsent</span><span class="sxs-lookup"><span data-stu-id="6436b-122">The "EnableGroupSpecificConsent" setting</span></span>

<span data-ttu-id="6436b-123">Этот параметр управляет разрешением пользователей в организации на доступ к приложениям, которые имеют доступ к данным компании в своих группах.</span><span class="sxs-lookup"><span data-stu-id="6436b-123">This setting controls whether users in your organization can consent to apps accessing company data for the groups that they own.</span></span> <span data-ttu-id="6436b-124">Этот параметр должен быть включен для того, чтобы владельцы команд дали согласие.</span><span class="sxs-lookup"><span data-stu-id="6436b-124">This setting must be enabled for team owners to give consent.</span></span> <span data-ttu-id="6436b-125">Сведения о том, как управлять этим параметром с помощью PowerShell, см. в сведениях о том, как настроить согласие владельца группы на доступ к приложениям, [которые имеют доступ к данным группы.](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)</span><span class="sxs-lookup"><span data-stu-id="6436b-125">For steps on how to manage this setting by using PowerShell, see [Configure group owner consent to apps accessing group data](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).</span></span>

### <a name="settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="6436b-126">Параметры в Центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6436b-126">Settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="6436b-127">Помимо параметров в Azure AD, параметры приложений [](manage-apps.md) для всей организации на странице "Управление приложениями" определяют, заблокировано ли приложение или разрешено на странице "Управление приложениями", а политика разрешений, назначенная владельцу группы, определяет, может ли владелец команды предоставить согласие. [](manage-apps.md#manage-org-wide-app-settings) [](manage-apps.md#allow-and-block-apps) [](teams-app-permission-policies.md)</span><span class="sxs-lookup"><span data-stu-id="6436b-127">In addition to settings in Azure AD, [org-wide app settings](manage-apps.md#manage-org-wide-app-settings) on the [Manage apps](manage-apps.md) page, whether an app is blocked or allowed on the [Manage apps](manage-apps.md#allow-and-block-apps) page, and the [app permission policy](teams-app-permission-policies.md) assigned to the team owner determine whether a team owner can give consent.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6436b-128">Изменение этих параметров не влияет на доступ к данным для приложений, которые уже получили согласие.</span><span class="sxs-lookup"><span data-stu-id="6436b-128">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="6436b-129">Например, если вы отключаете сторонние приложения в масштабе всей организации или блокируете определенные приложения, чтобы владельцы команд не предоставили согласие, эти изменения не удаляют уже предоставленный доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="6436b-129">For example, if you disable third-party apps org-wide or if you block specific apps to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a><span data-ttu-id="6436b-130">Параметр "Разрешить приложения сторонних разработчиков" в параметрах приложений для всей организации</span><span class="sxs-lookup"><span data-stu-id="6436b-130">The "Allow third party apps" setting in org-wide app settings</span></span>

<span data-ttu-id="6436b-131">Этот параметр приложения для всей организации контролирует возможность использования сторонних приложений пользователями в организации.</span><span class="sxs-lookup"><span data-stu-id="6436b-131">This org-wide app setting controls whether users in your organization can use third-party apps.</span></span> <span data-ttu-id="6436b-132">Этот параметр должен быть включиться, чтобы владельцы команд могли предоставить согласие.</span><span class="sxs-lookup"><span data-stu-id="6436b-132">This setting must be on to enable team owners to give consent.</span></span> <span data-ttu-id="6436b-133">Чтобы управлять этим параметром, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="6436b-133">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="6436b-134">В левой области навигации Центра администрирования Microsoft Teams перейдите в приложение **Teams**"Управление приложениями" и щелкните "Параметры приложения для всей  >   **организации".**</span><span class="sxs-lookup"><span data-stu-id="6436b-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
2. <span data-ttu-id="6436b-135">В **приложениях сторонних приложений** отключите или включите **разрешение сторонних приложений.**</span><span class="sxs-lookup"><span data-stu-id="6436b-135">Under **Third party apps**, turn off or turn on **Allow third party apps**.</span></span>

    ![Снимок экрана: параметр "Разрешить приложения сторонних приложений в Teams"](media/resource-specific-consent-org-wide-setting.png)

<span data-ttu-id="6436b-137">Чтобы изменения вступили в силу, может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="6436b-137">You may have to wait up to 24 hours for your changes to take effect.</span></span>

#### <a name="allow-or-block-the-app-at-the-org-level"></a><span data-ttu-id="6436b-138">Разрешение или блокировка приложения на уровне организации</span><span class="sxs-lookup"><span data-stu-id="6436b-138">Allow or block the app at the org level</span></span>

<span data-ttu-id="6436b-139">Если вы блокируете или [](manage-apps.md#allow-and-block-apps) разрешаете приложение на странице "Управление приложениями", это приложение блокируется или разрешено для всех пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="6436b-139">When you block or allow an app on the [Manage apps](manage-apps.md#allow-and-block-apps) page, that app is blocked or allowed for all users in your organization.</span></span> <span data-ttu-id="6436b-140">Владельцы команд могут дать согласие на это только в том случае, если это разрешено приложением.</span><span class="sxs-lookup"><span data-stu-id="6436b-140">Team owners can only give consent to an app if the app is allowed.</span></span> <span data-ttu-id="6436b-141">Чтобы разрешить или заблокировать приложение на уровне организации, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="6436b-141">To allow or block an app at the org level, do the following:</span></span>

1. <span data-ttu-id="6436b-142">В левой области навигации Центра администрирования Microsoft Teams перейдите в приложение **Teams**  >  **"Управление приложениями".**</span><span class="sxs-lookup"><span data-stu-id="6436b-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="6436b-143">На странице "Управление приложениями" выберите  приложение, а затем нажмите кнопку "Заблокировать", чтобы заблокировать его, или кнопку **"Разрешить",** чтобы разрешить.</span><span class="sxs-lookup"><span data-stu-id="6436b-143">On the Manage apps page, select the app, and then click **Block** to block it or click **Allow** to allow it.</span></span>

    ![Снимок экрана: заблокированные приложения в параметрах для всей организации](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a><span data-ttu-id="6436b-145">Политика разрешений для приложений, назначенная владельцу группы</span><span class="sxs-lookup"><span data-stu-id="6436b-145">App permission policy assigned to the team owner</span></span>

<span data-ttu-id="6436b-146">Владельцы команд могут предоставить согласие только тем приложениям, которые их политика разрешений разрешает им запускать.</span><span class="sxs-lookup"><span data-stu-id="6436b-146">Team owners can only give consent to apps that their app permission policy allows them to run.</span></span> <span data-ttu-id="6436b-147">Чтобы просмотреть политику разрешений приложений, назначенную владельцу группы, и управлять ее, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="6436b-147">To view and manage the app permission policy that's assigned to a team owner, do the following:</span></span>

1. <span data-ttu-id="6436b-148">В левой области навигации Центра администрирования Microsoft Teams перейдите в меню **"Пользователи".**</span><span class="sxs-lookup"><span data-stu-id="6436b-148">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="6436b-149">Дважды щелкните отображаемую имя владельца группы и выберите **"Политики".**</span><span class="sxs-lookup"><span data-stu-id="6436b-149">Double-click the display name of the team owner, and then click **Policies**.</span></span>
3. <span data-ttu-id="6436b-150">Политика, назначенная владельцу группы, указана в списке под **политикой разрешений приложений.**</span><span class="sxs-lookup"><span data-stu-id="6436b-150">The policy assigned to the team owner is listed under **App permission policy**.</span></span>
    - <span data-ttu-id="6436b-151">Чтобы назначить другую политику, нажмите кнопку **"Изменить"** и выберите политику, которую хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="6436b-151">To assign a different policy, click **Edit**, and then select the policy that you want to assign.</span></span>
    - <span data-ttu-id="6436b-152">Чтобы изменить параметры политики, назначенной владельцу группы, щелкните ее имя и внести нужные изменения.</span><span class="sxs-lookup"><span data-stu-id="6436b-152">To edit the settings of the policy that's assigned to the team owner, click the policy name, and then make the changes that you want.</span></span>  

## <a name="uploading-custom-apps"></a><span data-ttu-id="6436b-153">Отправка пользовательских приложений</span><span class="sxs-lookup"><span data-stu-id="6436b-153">Uploading custom apps</span></span>

<span data-ttu-id="6436b-154">При отправке настраиваемого приложения (известного также как неокладная загрузка), которое использует разрешение конкретного ресурса, оно должно быть загружено из клиента, в который оно устанавливается.</span><span class="sxs-lookup"><span data-stu-id="6436b-154">When uploading a custom app (also known sideloading) that uses resource-specific consent, the app must come from the tenant that it's being installed to.</span></span> <span data-ttu-id="6436b-155">Другими словами, регистрация в приложении Azure AD должна быть зарегистрирована в этом клиенте.</span><span class="sxs-lookup"><span data-stu-id="6436b-155">In other words, the Azure AD app registration must be from this tenant.</span></span> <span data-ttu-id="6436b-156">Глобальные администраторы исключаются из этого ограничения и могут загружать пользовательские приложения из любого клиента напрямую в группу (загрузку неоплаты) или в каталог приложений клиента.</span><span class="sxs-lookup"><span data-stu-id="6436b-156">Global admins are exempted from this restriction, and can upload custom apps from any tenant, either directly to a team (sideloading) or to the tenant app catalog.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6436b-157">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="6436b-157">Related topics</span></span>

- [<span data-ttu-id="6436b-158">Доступные разрешения RSC</span><span class="sxs-lookup"><span data-stu-id="6436b-158">Available RSC permissions</span></span>](https://aka.ms/teams-rsc)
- [<span data-ttu-id="6436b-159">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="6436b-159">Microsoft Graph</span></span>](https://developer.microsoft.com/graph)
- [<span data-ttu-id="6436b-160">Управление приложениями в Центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6436b-160">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="6436b-161">Управление политиками разрешений для приложений в Teams</span><span class="sxs-lookup"><span data-stu-id="6436b-161">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
