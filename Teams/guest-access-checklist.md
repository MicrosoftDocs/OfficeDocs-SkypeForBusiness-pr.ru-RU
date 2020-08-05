---
title: Контрольный список гостевого доступа Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: Узнайте о том, как включить и настроить гостевой доступ в Microsoft Teams в качестве администратора глобальной или Teaming.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4305f8f03f806be1a453e037620c6e16e71ac4dc
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552267"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="d74f8-103">Контрольный список гостевого доступа Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d74f8-103">Microsoft Teams guest access checklist</span></span>
=========================================

<span data-ttu-id="d74f8-104">Используйте этот контрольный список, чтобы помочь вам включить и настроить гостевой доступ в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d74f8-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span> <span data-ttu-id="d74f8-105">Для внесения этих изменений вам необходимо быть глобальным администратором или администратором команд.</span><span class="sxs-lookup"><span data-stu-id="d74f8-105">You need to be a Global Administrator or a Teams Administrator to make these changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d74f8-106">Чтобы изменения вступили в силу, может потребоваться подождать несколько часов.</span><span class="sxs-lookup"><span data-stu-id="d74f8-106">You may have to wait a few hours for your changes to take effect.</span></span>

<span data-ttu-id="d74f8-107">Посмотрите это короткое видео (5:31 минут), чтобы узнать, как включить гостевой доступ в Microsoft 365, включая Команды.</span><span class="sxs-lookup"><span data-stu-id="d74f8-107">Watch this short video (5:31 minutes) to see how to turn on guest access throughout Microsoft 365, including Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="d74f8-108">Шаг 1. Включите гостевой доступ на уровне всей команды.</span><span class="sxs-lookup"><span data-stu-id="d74f8-108">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="d74f8-109">Вы должны быть администратором службы Teams, чтобы внести эти изменения.</span><span class="sxs-lookup"><span data-stu-id="d74f8-109">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="d74f8-110">Сведения о том, как получить роли администраторов и разрешения, можно найти [в статье Использование ролей администратора Teams для управления группами](https://docs.microsoft.com/microsoftteams/using-admin-roles) .</span><span class="sxs-lookup"><span data-stu-id="d74f8-110">See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="d74f8-111">В Центре администрирования команд выберите **Настройки всей организации** > **Гостевой доступ**.</span><span class="sxs-lookup"><span data-stu-id="d74f8-111">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="d74f8-112">Установите переключатель **Разрешить гостевой доступ в Microsoft Teams** на **Вкл**.</span><span class="sxs-lookup"><span data-stu-id="d74f8-112">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Снимок экрана показывает пример переключения настроек Teams](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="d74f8-114">На этой же странице включите или отключите параметры **вызовов**, **собраний** и **обмена сообщениями** для гостей.</span><span class="sxs-lookup"><span data-stu-id="d74f8-114">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="d74f8-115">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d74f8-115">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="d74f8-116">Если вы используете параметры по умолчанию в Azure Active Directory, SharePoint Online и Microsoft 365 Groups, возможно, вы захотите настроить гостевой доступ.</span><span class="sxs-lookup"><span data-stu-id="d74f8-116">If you're using default settings in Azure Active Directory, SharePoint Online, and Microsoft 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="d74f8-117">В этом случае вы можете пропустить остальные шаги.</span><span class="sxs-lookup"><span data-stu-id="d74f8-117">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="d74f8-118">Если вы не уверены в том, что вы используете пользовательские параметры для AAD, SharePoint Online или Microsoft 365, следуйте дальнейшим указаниям в этом контрольном списке.</span><span class="sxs-lookup"><span data-stu-id="d74f8-118">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Microsoft 365 Groups, continue with the rest of the steps in this checklist.</span></span>

## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="d74f8-119">Шаг 2. Настройка бизнес-параметров Azure AD</span><span class="sxs-lookup"><span data-stu-id="d74f8-119">Step 2: Configure Azure AD business-to-business settings</span></span>

<span data-ttu-id="d74f8-120">Это параметры Azure AD, которые поддерживают гостевой доступ в командах.</span><span class="sxs-lookup"><span data-stu-id="d74f8-120">These are the Azure AD settings that support guest access in Teams.</span></span> <span data-ttu-id="d74f8-121">После настройки этих параметров вы сможете [добавлять](add-guests.md) и [управлять](manage-guests.md) гостями в командах.</span><span class="sxs-lookup"><span data-stu-id="d74f8-121">Once these settings are configured, you'll be able to [add](add-guests.md) and [manage guests](manage-guests.md) in Teams.</span></span>

1. <span data-ttu-id="d74f8-122">Войдите на [портал Azure](https://portal.azure.com) как администратор клиента.</span><span class="sxs-lookup"><span data-stu-id="d74f8-122">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="d74f8-123">Выберите **Azure Active Directory** > **пользователи** > **параметры пользователей**.</span><span class="sxs-lookup"><span data-stu-id="d74f8-123">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="d74f8-124">В разделе **Внешние пользователи** выберите **Управление параметрами внешней совместной работы**.</span><span class="sxs-lookup"><span data-stu-id="d74f8-124">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="d74f8-125">**Параметры внешнего сотрудничества** также доступны на странице **Организационные отношения**.</span><span class="sxs-lookup"><span data-stu-id="d74f8-125">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="d74f8-126">В Azure Active Directory в разделе **Управление** перейдите в раздел **организационные отношения** > \*\*Параметры \*\*.</span><span class="sxs-lookup"><span data-stu-id="d74f8-126">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="d74f8-127">На странице **параметров внешнего сотрудничества** выберите политики, которые вы хотите включить.</span><span class="sxs-lookup"><span data-stu-id="d74f8-127">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

    - <span data-ttu-id="d74f8-128">**Разрешения для гостевых пользователей ограничены**: эта политика определяет разрешения для гостей в вашем каталоге.</span><span class="sxs-lookup"><span data-stu-id="d74f8-128">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="d74f8-129">Выберите **Да**, чтобы заблокировать гостей от определенных задач каталога, таких как перечисление пользователей, групп или других ресурсов каталога.</span><span class="sxs-lookup"><span data-stu-id="d74f8-129">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="d74f8-130">Выберите **Нет**, чтобы предоставить гостям тот же доступ к данным каталога, что и обычным пользователям в вашем каталоге.</span><span class="sxs-lookup"><span data-stu-id="d74f8-130">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
     - <span data-ttu-id="d74f8-131">**Администраторы и пользователи в роли приглашающего гостя могут приглашать**: Чтобы разрешить администраторам и пользователям в роли приглашающего гостя приглашать гостей, установите для этой политики значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="d74f8-131">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
     - <span data-ttu-id="d74f8-132">**Участники могут приглашать других пользователей**. Чтобы разрешить пользователям, не являющимся администраторами каталога, приглашать гостей, присвойте этой политике значение **Да** (рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="d74f8-132">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="d74f8-133">Если вы хотите, чтобы только администраторы могли добавлять гостей, можно присвоить этой политике значение **Нет**.</span><span class="sxs-lookup"><span data-stu-id="d74f8-133">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="d74f8-134">Имейте в виду, что присвоение значения **Нет** ограничит гостевое взаимодействие для владельцев команд, не являющихся администраторами. Они смогут добавлять только тех гостей Teams, которые уже добавлены администратором в AAD.</span><span class="sxs-lookup"><span data-stu-id="d74f8-134">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
     - <span data-ttu-id="d74f8-135">**Гости могут приглашать**: чтобы разрешить гостям приглашать других гостей, установите для этой политики значение **да**.</span><span class="sxs-lookup"><span data-stu-id="d74f8-135">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="d74f8-136">В настоящее время в Teams не поддерживается роль приглашающего гостей, поэтому даже если вы установите для параметра **Гости могут приглашать** значение **Да**, гости не смогут приглашать других гостей в Teams.</span><span class="sxs-lookup"><span data-stu-id="d74f8-136">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
     - <span data-ttu-id="d74f8-137">**Включить одноразовый пароль электронной почты для гостей (предварительный просмотр)**: Дополнительные сведения о функции одноразового пароля см. В разделе [Аутентификация одноразового пароля электронной почты (предварительный просмотр)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span><span class="sxs-lookup"><span data-stu-id="d74f8-137">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
     - <span data-ttu-id="d74f8-138">**Ограничения для совместной работы**. Дополнительные сведения о том, как разрешить или заблокировать приглашения на доступ к определенным доменам, см. в статье [разрешения и блокирование приглашений для пользователей B2B из определенных организаций](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="d74f8-138">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
        > [!NOTE]
        > <span data-ttu-id="d74f8-139">Ограничения для совместной работы см. в статье [включение внешней совместной работы в B2B и управление пользователями, которые могут приглашать гостей](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="d74f8-139">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

    <span data-ttu-id="d74f8-140">Дополнительные сведения об управлении возможностью приглашения гостей см. в статье [Делегирование приглашений для службы совместной работы Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="d74f8-140">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="step-3-configure-microsoft-365-groups"></a><span data-ttu-id="d74f8-141">Шаг 3: Настройка групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d74f8-141">Step 3: Configure Microsoft 365 Groups</span></span>

1. <span data-ttu-id="d74f8-142">В центре администрирования Microsoft 365 **перейдите в раздел Параметры**  >  **Организации**и выберите пункт **службы**, а затем — **группы Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="d74f8-142">In the Microsoft 365 admin center, go to **Settings** > **Org Settings**, click **Services**, and then select **Microsoft 365 Groups**.</span></span>

     ![Снимок экрана: параметры групп Microsoft 365](media/guest-access-checklist-services-settings.png)
2. <span data-ttu-id="d74f8-144">Убедитесь, что установлен флажок **Разрешить членам группы за пределами организации доступ к содержимому группы**.</span><span class="sxs-lookup"><span data-stu-id="d74f8-144">Make sure that the **Let group members outside the organization access group content** check box is selected.</span></span> <span data-ttu-id="d74f8-145">Если этот параметр не выбран, гости не смогут получить доступ к содержимому группы.</span><span class="sxs-lookup"><span data-stu-id="d74f8-145">If this setting is not selected, guests won't be able to access any group content.</span></span>

    ![Снимок экрана: параметры групп Microsoft 365](media/guest-access-checklist-office365.png)
3. <span data-ttu-id="d74f8-147">Убедитесь, что установлен флажок **Позвольте владельцам групп добавлять людей вне организации в группы**.</span><span class="sxs-lookup"><span data-stu-id="d74f8-147">Make sure that the **Let group owners add people outside the organization to groups** check box is selected.</span></span> <span data-ttu-id="d74f8-148">Если этот параметр не выбран, владельцы команд не смогут добавлять новых гостей.</span><span class="sxs-lookup"><span data-stu-id="d74f8-148">If this setting is not selected, team owners won't be able to add new guests.</span></span> <span data-ttu-id="d74f8-149">Как минимум, этот параметр должен быть включен для поддержки гостевого доступа.</span><span class="sxs-lookup"><span data-stu-id="d74f8-149">At a minimum, this setting must be on to support guest access.</span></span>

<span data-ttu-id="d74f8-150">Подробные инструкции по настройке этих параметров можно найти в разделе [Управление гостевым доступом в группах microsoft 365](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) и [Управление гостевым доступом в группах Microsoft 365](Teams-dependencies.md#control-guest-access-in-microsoft-365-groups).</span><span class="sxs-lookup"><span data-stu-id="d74f8-150">For detailed instructions about configuring these settings, see [Manage guest access in Microsoft 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Microsoft 365 Groups](Teams-dependencies.md#control-guest-access-in-microsoft-365-groups).</span></span>

## <a name="step-4-configure-sharing-in-microsoft-365"></a><span data-ttu-id="d74f8-151">Шаг 4: Настройка общего доступ в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d74f8-151">Step 4: Configure sharing in Microsoft 365</span></span>

<span data-ttu-id="d74f8-152">Убедитесь, что пользователи могут добавлять гостей.</span><span class="sxs-lookup"><span data-stu-id="d74f8-152">Make sure that users can add guests.</span></span> <span data-ttu-id="d74f8-153">Вот как это сделать:</span><span class="sxs-lookup"><span data-stu-id="d74f8-153">Here's how:</span></span>

1. <span data-ttu-id="d74f8-154">В центре администрирования Microsoft 365 **перейдите в раздел Параметры**  >  **Организации**, выберите раздел **Безопасность & конфиденциальность**и нажмите кнопку **общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="d74f8-154">In the Microsoft 365 admin center, go to **Settings** > **Org Settings**, click **Security & privacy**, and then select **Sharing**.</span></span>

     ![Снимок экрана показывает пример настройки служб](media/guest-access-checklist-security-privacy-settings.png)

2. <span data-ttu-id="d74f8-156">Установите флажок **Разрешить пользователям добавлять новых гостей в эту организацию** и нажмите **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="d74f8-156">Select the **Let users add new guests to this organization** check box, and then click **Save changes**.</span></span>

     ![Снимок экрана показывает пример переключения настроек общего доступа](media/guest-access-checklist-sharing-setting.png)

    > [!NOTE]
    > <span data-ttu-id="d74f8-158">Этот параметр эквивалентен параметру **Участники могут пригласить** в **настройках пользователя** > **Внешние пользователи** в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d74f8-158">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="d74f8-159">Шаг 5. Проверка настроек общего доступа в SharePoint</span><span class="sxs-lookup"><span data-stu-id="d74f8-159">Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="d74f8-160">Войдите в Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d74f8-160">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="d74f8-161">В **Центрах администрирования** выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="d74f8-161">Under **Admin centers**, select  **SharePoint**.</span></span>
3. <span data-ttu-id="d74f8-162">В новом центре администрирования SharePoint в разделе **Сайты** выберите **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="d74f8-162">In the new SharePoint admin center,  under **Sites**, select **Active sites**.</span></span>

    ![Активные сайты в центре администрирования SharePoint](media/guest-access-checklist-SPOSettings0.png)

3. <span data-ttu-id="d74f8-164">Выберите сайт и нажмите **Общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="d74f8-164">Select the site, and then click **Sharing**.</span></span>
4. <span data-ttu-id="d74f8-165">Убедитесь, что для этого параметра установлено значение **Любой** или **Новые и существующие гости**.</span><span class="sxs-lookup"><span data-stu-id="d74f8-165">Make sure that the option is set to **Anyone** or **New and existing guests**.</span></span>

     ![Снимок экрана показывает пример переключения параметров SharePoint Online](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="d74f8-167">Шаг 6: Настройте права гостя</span><span class="sxs-lookup"><span data-stu-id="d74f8-167">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="d74f8-168">В приложении Teams на уровне отдельной группы настройте гостевые разрешения, которые определяют, могут ли гости создавать, обновлять или удалять каналы.</span><span class="sxs-lookup"><span data-stu-id="d74f8-168">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="d74f8-169">Администраторы команд, а также владельцы команд могут настроить эти параметры.</span><span class="sxs-lookup"><span data-stu-id="d74f8-169">Teams admins as well as team owners can configure these settings.</span></span>

![Снимок экрана показывает пример переключения настроек команды / канала](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="d74f8-171">Чтобы узнать больше о гостевом доступе, см. [Гостевой доступ в Teams](guest-access.md) и [Включите или отключите гостевой доступ к Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="d74f8-171">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>

## <a name="step-7-turn-on-anonymous-users-can-join-a-meeting-if-you-want-guests-to-join-meetings"></a><span data-ttu-id="d74f8-172">Шаг 7: Включение и отключение анонимных пользователей для присоединения к собраниям, если вы хотите присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="d74f8-172">Step 7: Turn on "Anonymous users can join a meeting" if you want guests to join meetings</span></span>

<span data-ttu-id="d74f8-173">Если вы хотите присоединиться к собраниям, включите **анонимных пользователей, которые могут присоединиться** к параметрам собрания в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d74f8-173">If you want guests to join meetings, turn on the **Anonymous users can join a meeting** setting in the Microsoft Teams admin center.</span></span> 

1. <span data-ttu-id="d74f8-174">В левой области навигации центра администрирования Microsoft Teams перейдите к разделу **Meetings**  >  **Параметры собраний**для собраний.</span><span class="sxs-lookup"><span data-stu-id="d74f8-174">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting settings**.</span></span>

2. <span data-ttu-id="d74f8-175">В разделе **Участники** включите **Анонимные пользователи могут присоединиться к собранию**.</span><span class="sxs-lookup"><span data-stu-id="d74f8-175">Under **Participants**, turn on **Anonymous users can join a meeting**.</span></span>

<span data-ttu-id="d74f8-176">Дополнительные сведения можно найти [в разделе Управление параметрами собраний в Teams](meeting-settings-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="d74f8-176">To learn more, see [Manage meeting settings in Teams](meeting-settings-in-teams.md).</span></span> 

## <a name="troubleshooting"></a><span data-ttu-id="d74f8-177">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="d74f8-177">Troubleshooting</span></span>

<span data-ttu-id="d74f8-178">Если у вас есть проблемы с настройкой гостевого доступа или добавлением гостей в Teams, используйте эти ресурсы, чтобы помочь вам:</span><span class="sxs-lookup"><span data-stu-id="d74f8-178">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="d74f8-179">Устранять проблемы с гостевым доступом в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d74f8-179">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="d74f8-180">Устранение неисправностей Teams</span><span class="sxs-lookup"><span data-stu-id="d74f8-180">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
