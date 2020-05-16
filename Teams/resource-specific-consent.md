---
title: Согласие на конкретные ресурсы в Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Узнайте о параметрах, которые необходимо настроить, чтобы управлять тем, могут ли владельцы групп в Организации предоставлять согласие на работу с приложениями.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54a0565f5126c899ed5fbf9527aa30f83c3bee3b
ms.sourcegitcommit: 296aeac481f901eb9d52b4f12a8c037afc49fa77
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "44256599"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a><span data-ttu-id="147e1-103">Согласие на конкретные ресурсы в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="147e1-103">Resource-specific consent in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="147e1-104">Согласие на определенные ресурсы в Microsoft Teams позволяет владельцам групп предоставлять согласие на доступ к данным о группе для приложений.</span><span class="sxs-lookup"><span data-stu-id="147e1-104">Resource-specific consent in Microsoft Teams lets team owners give consent to apps to access team data.</span></span> <span data-ttu-id="147e1-105">Примеры такого доступа включают возможность чтения сообщений канала, создание и удаление каналов, а также создание и удаление вкладок каналов.</span><span class="sxs-lookup"><span data-stu-id="147e1-105">Examples of such access include the ability to read channel messages, create and delete channels, and create and remove channel tabs.</span></span>

<span data-ttu-id="147e1-106">Администраторы могут предоставить согласие на доступ к параметрам, настроенным с помощью модуля PowerShell Active Directory (Azure AD) либо на портале Azure и в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="147e1-106">As an admin, you control whether team owners in your organization can give consent through settings that you configure by using the Azure Active Directory (Azure AD) PowerShell module or the Azure portal and the Microsoft Teams admin center.</span></span>  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a><span data-ttu-id="147e1-107">Определение того, может ли владелец группы предоставлять согласие на приложения</span><span class="sxs-lookup"><span data-stu-id="147e1-107">Set whether team owners can give consent to apps</span></span>

<span data-ttu-id="147e1-108">Ниже указаны параметры, которые необходимо настроить, чтобы управлять тем, может ли владелец группы предоставлять согласие на приложения.</span><span class="sxs-lookup"><span data-stu-id="147e1-108">Here are the settings that you must set to control whether team owners can give consent to apps.</span></span> <span data-ttu-id="147e1-109">Обязательно ознакомьтесь со всеми следующими параметрами.</span><span class="sxs-lookup"><span data-stu-id="147e1-109">Be sure to review all the following settings.</span></span>

### <a name="settings-in-azure-ad"></a><span data-ttu-id="147e1-110">Параметры в Azure AD</span><span class="sxs-lookup"><span data-stu-id="147e1-110">Settings in Azure AD</span></span>

<span data-ttu-id="147e1-111">Следующие два параметра определяют, могут ли владельцы групп предоставлять согласие на приложения.</span><span class="sxs-lookup"><span data-stu-id="147e1-111">The following two settings determine whether team owners can give consent to apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="147e1-112">Изменение любого из этих параметров не влияет на доступ к данным для приложений, которым уже предоставлено согласие.</span><span class="sxs-lookup"><span data-stu-id="147e1-112">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="147e1-113">Например, если вы настроили эти параметры, чтобы запретить владельцам групп получать разрешения, эти изменения не удаляют доступ к данным, который уже предоставлен.</span><span class="sxs-lookup"><span data-stu-id="147e1-113">For example, if you configure these settings to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a><span data-ttu-id="147e1-114">Параметр "пользователи могут получать согласие на приложения, которые получают данные компании от их имени"</span><span class="sxs-lookup"><span data-stu-id="147e1-114">The "Users can consent to apps accessing company data on their behalf" setting</span></span>

<span data-ttu-id="147e1-115">Этот параметр определяет, могут ли пользователи в вашей организации получать согласие на доступ к приложениям от их имени.</span><span class="sxs-lookup"><span data-stu-id="147e1-115">This setting controls whether users in your organization can consent to apps on their behalf.</span></span> <span data-ttu-id="147e1-116">Чтобы разрешить владельцам групп предоставлять согласие, этот параметр должен иметь значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="147e1-116">To enable team owners to give consent, this setting must be set to **Yes**.</span></span> <span data-ttu-id="147e1-117">Чтобы изменить этот параметр, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="147e1-117">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="147e1-118">На портале Azure перейдите в раздел **Enterprise applications**  >  **Параметры пользователя**для корпоративных приложений.</span><span class="sxs-lookup"><span data-stu-id="147e1-118">In the Azure portal, go to **Enterprise applications** > **User settings**.</span></span>
2. <span data-ttu-id="147e1-119">В разделе **корпоративные приложения** **пользователи могут получать согласие на то, что приложения обращаются к данным компании от их имени** к " **нет** **" или "Да"**.</span><span class="sxs-lookup"><span data-stu-id="147e1-119">Under **Enterprise applications**, set **Users can consent to apps accessing company data on their behalf** to **No** or **Yes**.</span></span>

<span data-ttu-id="147e1-120">Вы также можете управлять этим параметром с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="147e1-120">You can also manage this setting using PowerShell.</span></span> <span data-ttu-id="147e1-121">Дополнительные сведения можно найти в разделе [Настройка пользовательского содержимого для приложений](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).</span><span class="sxs-lookup"><span data-stu-id="147e1-121">To learn more, see [Configure user content to applications](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).</span></span>

#### <a name="the-enablegroupspecificconsent-setting"></a><span data-ttu-id="147e1-122">Параметр "EnableGroupSpecificConsent"</span><span class="sxs-lookup"><span data-stu-id="147e1-122">The "EnableGroupSpecificConsent" setting</span></span>

<span data-ttu-id="147e1-123">Этот параметр определяет, могут ли пользователи в вашей организации получать согласие на доступ к данным компании для тех групп, которыми они владеют.</span><span class="sxs-lookup"><span data-stu-id="147e1-123">This setting controls whether users in your organization can consent to apps accessing company data for the groups that they own.</span></span> <span data-ttu-id="147e1-124">Этот параметр должен быть включен, если владельцам групп будет предоставлено согласие.</span><span class="sxs-lookup"><span data-stu-id="147e1-124">This setting must be enabled for team owners to give consent.</span></span> <span data-ttu-id="147e1-125">Инструкции по управлению этим параметром с помощью PowerShell можно найти в статье [Настройка согласия владельца группы для приложений](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data), использующих доступ к данным о группах.</span><span class="sxs-lookup"><span data-stu-id="147e1-125">For steps on how to manage this setting by using PowerShell, see [Configure group owner consent to apps accessing group data](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).</span></span>

### <a name="settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="147e1-126">Параметры в центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="147e1-126">Settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="147e1-127">В дополнение к параметрам в Azure AD, [Параметры приложения в масштабах Организации](manage-apps.md#manage-org-wide-app-settings) на странице [Manage Apps](manage-apps.md) ( [Управление приложениями)](manage-apps.md#allow-and-block-apps) , а также в том [случае, если](teams-app-permission-policies.md) приложение заблокировано или разрешено для владельца группы, определяет, может ли владелец группы получить согласие.</span><span class="sxs-lookup"><span data-stu-id="147e1-127">In addition to settings in Azure AD, [org-wide app settings](manage-apps.md#manage-org-wide-app-settings) on the [Manage apps](manage-apps.md) page, whether an app is blocked or allowed on the [Manage apps](manage-apps.md#allow-and-block-apps) page, and the [app permission policy](teams-app-permission-policies.md) assigned to the team owner determine whether a team owner can give consent.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="147e1-128">Изменение любого из этих параметров не влияет на доступ к данным для приложений, которым уже предоставлено согласие.</span><span class="sxs-lookup"><span data-stu-id="147e1-128">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="147e1-129">Например, если отключить сторонние приложения или заблокировать определенные приложения, чтобы не допустить согласие владельцам групп, эти изменения не удаляют доступ к данным, который уже предоставлен.</span><span class="sxs-lookup"><span data-stu-id="147e1-129">For example, if you disable third-party apps org-wide or if you block specific apps to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a><span data-ttu-id="147e1-130">Параметр "Разрешить сторонние приложения" в параметрах приложения в масштабах Организации</span><span class="sxs-lookup"><span data-stu-id="147e1-130">The "Allow third party apps" setting in org-wide app settings</span></span>

<span data-ttu-id="147e1-131">Этот параметр приложения на уровне Организации определяет, могут ли пользователи в вашей организации использовать сторонние приложения.</span><span class="sxs-lookup"><span data-stu-id="147e1-131">This org-wide app setting controls whether users in your organization can use third-party apps.</span></span> <span data-ttu-id="147e1-132">Этот параметр должен быть включен, чтобы предоставить владельцам групп разрешение на согласие.</span><span class="sxs-lookup"><span data-stu-id="147e1-132">This setting must be on to enable team owners to give consent.</span></span> <span data-ttu-id="147e1-133">Чтобы изменить этот параметр, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="147e1-133">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="147e1-134">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **приложения Teams**  >  **Управление приложениями**, а затем выберите **Параметры приложения для всей Организации**.</span><span class="sxs-lookup"><span data-stu-id="147e1-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
2. <span data-ttu-id="147e1-135">В разделе **сторонние приложения**отключите или включите **разрешение приложений третьих лиц**.</span><span class="sxs-lookup"><span data-stu-id="147e1-135">Under **Third party apps**, turn off or turn on **Allow third party apps**.</span></span>

    ![Снимок экрана: параметр "Разрешить сторонние приложения в Teams"](media/resource-specific-consent-org-wide-setting.png)

<span data-ttu-id="147e1-137">Чтобы изменения вступили в силу, может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="147e1-137">You may have to wait up to 24 hours for your changes to take effect.</span></span>

#### <a name="allow-or-block-the-app-at-the-org-level"></a><span data-ttu-id="147e1-138">Разрешение или блокирование приложения на уровне Организации</span><span class="sxs-lookup"><span data-stu-id="147e1-138">Allow or block the app at the org level</span></span>

<span data-ttu-id="147e1-139">Если вы блокируете или разрешаете приложение на странице " [Управление приложениями](manage-apps.md#allow-and-block-apps) ", это приложение заблокировано или разрешено для всех пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="147e1-139">When you block or allow an app on the [Manage apps](manage-apps.md#allow-and-block-apps) page, that app is blocked or allowed for all users in your organization.</span></span> <span data-ttu-id="147e1-140">Владельцы группы могут предоставить согласие на доступ к приложению только в том случае, если приложение разрешено.</span><span class="sxs-lookup"><span data-stu-id="147e1-140">Team owners can only give consent to an app if the app is allowed.</span></span> <span data-ttu-id="147e1-141">Чтобы разрешить или заблокировать приложение на уровне Организации, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="147e1-141">To allow or block an app at the org level, do the following:</span></span>

1. <span data-ttu-id="147e1-142">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **приложения Teams**  >  **Управление приложениями**.</span><span class="sxs-lookup"><span data-stu-id="147e1-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="147e1-143">На странице Manage Apps (Управление приложениями) выберите приложение, а затем выберите команду **блокировать** , чтобы заблокировать ее **или разрешить.**</span><span class="sxs-lookup"><span data-stu-id="147e1-143">On the Manage apps page, select the app, and then click **Block** to block it or click **Allow** to allow it.</span></span>

    ![Снимок экрана: заблокированные приложения в параметрах уровня Организации](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a><span data-ttu-id="147e1-145">Политика разрешений на доступ к приложениям, назначенная владельцу группы</span><span class="sxs-lookup"><span data-stu-id="147e1-145">App permission policy assigned to the team owner</span></span>

<span data-ttu-id="147e1-146">Владельцы команды могут предоставить согласие на работу с приложениями, которые их политика разрешений на доступ к приложениям позволяет им выполняться.</span><span class="sxs-lookup"><span data-stu-id="147e1-146">Team owners can only give consent to apps that their app permission policy allows them to run.</span></span> <span data-ttu-id="147e1-147">Чтобы просмотреть и настроить политику разрешений приложений, назначенную владельцу группы, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="147e1-147">To view and manage the app permission policy that's assigned to a team owner, do the following:</span></span>

1. <span data-ttu-id="147e1-148">В левой области навигации центра администрирования Microsoft Teams перейдите к разделу **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="147e1-148">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="147e1-149">Дважды щелкните отображаемое имя владельца команды и выберите пункт **политики**.</span><span class="sxs-lookup"><span data-stu-id="147e1-149">Double-click the display name of the team owner, and then click **Policies**.</span></span>
3. <span data-ttu-id="147e1-150">Политика, назначенная владельцу группы, указана в разделе **политика разрешений на доступ к приложениям**.</span><span class="sxs-lookup"><span data-stu-id="147e1-150">The policy assigned to the team owner is listed under **App permission policy**.</span></span>
    - <span data-ttu-id="147e1-151">Чтобы назначить другую политику, нажмите кнопку **изменить**, а затем выберите политику, которую вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="147e1-151">To assign a different policy, click **Edit**, and then select the policy that you want to assign.</span></span>
    - <span data-ttu-id="147e1-152">Чтобы изменить параметры политики, назначенной владельцу группы, щелкните имя политики и внесите необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="147e1-152">To edit the settings of the policy that's assigned to the team owner, click the policy name, and then make the changes that you want.</span></span>  

## <a name="uploading-custom-apps"></a><span data-ttu-id="147e1-153">Отправка настраиваемых приложений</span><span class="sxs-lookup"><span data-stu-id="147e1-153">Uploading custom apps</span></span>

<span data-ttu-id="147e1-154">При загрузке настраиваемого приложения (также известной для загрузки неопубликованных приложений), которое использует согласие на ресурс, приложение должно быть получено от клиента, на который оно установлено.</span><span class="sxs-lookup"><span data-stu-id="147e1-154">When uploading a custom app (also known sideloading) that uses resource-specific consent, the app must come from the tenant that it's being installed to.</span></span> <span data-ttu-id="147e1-155">Другими словами, регистрация приложения Azure AD должна быть из этого клиента.</span><span class="sxs-lookup"><span data-stu-id="147e1-155">In other words, the Azure AD app registration must be from this tenant.</span></span> <span data-ttu-id="147e1-156">Глобальные администраторы исключаются из этого ограничения и могут отправлять пользовательские приложения из любого клиента либо непосредственно в группу (в неопубликованных), либо в каталог приложений клиента.</span><span class="sxs-lookup"><span data-stu-id="147e1-156">Global admins are exempted from this restriction, and can upload custom apps from any tenant, either directly to a team (sideloading) or to the tenant app catalog.</span></span>

## <a name="related-topics"></a><span data-ttu-id="147e1-157">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="147e1-157">Related topics</span></span>

- [<span data-ttu-id="147e1-158">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="147e1-158">Microsoft Graph</span></span>](https://developer.microsoft.com/graph)
- [<span data-ttu-id="147e1-159">Управление приложениями в центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="147e1-159">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="147e1-160">Управление политиками разрешений для приложений в Teams</span><span class="sxs-lookup"><span data-stu-id="147e1-160">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
