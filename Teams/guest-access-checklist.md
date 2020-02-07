---
title: Контрольный список для гостевого доступа в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: С помощью этого контрольного списка вы можете настроить гостевой доступ в Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b60b0e5f0972d862ec1b945f1b267b04faae9a8a
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41833259"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="55d8f-103">Контрольный список для гостевого доступа в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55d8f-103">Microsoft Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="55d8f-104">С помощью этого контрольного списка вы можете включить и настроить гостевой доступ в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="55d8f-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span> <span data-ttu-id="55d8f-105">Вы должны быть глобальным администратором или администратором Teams, чтобы внести эти изменения.</span><span class="sxs-lookup"><span data-stu-id="55d8f-105">You need to be a Global Administrator or a Teams Administrator to make these changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="55d8f-106">Чтобы изменения вступили в силу, возможно, потребуется подождать до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="55d8f-106">You may have to wait up to 24 hours for your changes to take effect.</span></span> 

<span data-ttu-id="55d8f-107">В этом коротком видеоролике (5:31 минут) вы узнаете, как включить гостевой доступ в Microsoft 365, в том числе в Teams.</span><span class="sxs-lookup"><span data-stu-id="55d8f-107">Watch this short video (5:31 minutes) to see how to turn on guest access throughout Microsoft 365, including Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="55d8f-108">Действие 1: Включите гостевой доступ на уровне Организации в группе "Общие"</span><span class="sxs-lookup"><span data-stu-id="55d8f-108">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="55d8f-109">Чтобы включить гостевой доступ, перейдите в **центр администрирования Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="55d8f-109">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="55d8f-110">В центре администрирования Teams выберите > \*\*\*\* параметры для **всей Организации**.</span><span class="sxs-lookup"><span data-stu-id="55d8f-110">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="55d8f-111">Установите переключатель **Разрешить гостевой доступ в Microsoft Teams** . \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="55d8f-111">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Снимок экрана, на котором показан пример переключения параметров группы](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="55d8f-113">На этой же странице включите или отключите параметры **звонков**, **собраний**и **сообщений** для гостей.</span><span class="sxs-lookup"><span data-stu-id="55d8f-113">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="55d8f-114">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="55d8f-114">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="55d8f-115">Если вы используете параметры по умолчанию в Azure Active Directory, SharePoint Online и групп Office 365, возможно, вы захотите настроить гостевой доступ.</span><span class="sxs-lookup"><span data-stu-id="55d8f-115">If you're using default settings in Azure Active Directory, SharePoint Online, and Office 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="55d8f-116">В этом случае вы можете пропустить оставшиеся шаги.</span><span class="sxs-lookup"><span data-stu-id="55d8f-116">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="55d8f-117">Если вы не уверены в том, что вы используете пользовательские параметры для AAD, SharePoint Online или групп Office 365, следуйте дальнейшим указаниям в этом контрольном списке.</span><span class="sxs-lookup"><span data-stu-id="55d8f-117">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Office 365 Groups, continue with the rest of the steps in this checklist.</span></span>

## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="55d8f-118">Действие 2: Настройка параметров Azure AD для бизнеса-Бизнес</span><span class="sxs-lookup"><span data-stu-id="55d8f-118">Step 2: Configure Azure AD business-to-business settings</span></span>

<span data-ttu-id="55d8f-119">Это параметры Azure AD, поддерживающие гостевой доступ в Teams.</span><span class="sxs-lookup"><span data-stu-id="55d8f-119">These are the Azure AD settings that support guest access in Teams.</span></span> <span data-ttu-id="55d8f-120">После настройки этих параметров вы сможете [добавлять](add-guests.md) гостей в Teams и [управлять ими](manage-guests.md) .</span><span class="sxs-lookup"><span data-stu-id="55d8f-120">Once these settings are configured, you'll be able to [add](add-guests.md) and [manage guests](manage-guests.md) in Teams.</span></span>

1. <span data-ttu-id="55d8f-121">Войдите на [портал Azure](https://portal.azure.com) как администратор клиента.</span><span class="sxs-lookup"><span data-stu-id="55d8f-121">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="55d8f-122">Выберите**Параметры пользователя**для**пользователей** >  **Azure Active Directory** > .</span><span class="sxs-lookup"><span data-stu-id="55d8f-122">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="55d8f-123">В разделе **внешние пользователи**выберите **Управление внешними параметрами совместной работы**.</span><span class="sxs-lookup"><span data-stu-id="55d8f-123">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="55d8f-124">**Внешние параметры совместной работы** также доступны на странице " **организационные связи** ".</span><span class="sxs-lookup"><span data-stu-id="55d8f-124">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="55d8f-125">В службе Azure Active Directory в разделе **Управление**выберите пункт**Параметры** **организационных связей** > .</span><span class="sxs-lookup"><span data-stu-id="55d8f-125">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="55d8f-126">На странице **внешние параметры совместной работы** выберите политики, которые вы хотите включить.</span><span class="sxs-lookup"><span data-stu-id="55d8f-126">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

    - <span data-ttu-id="55d8f-127">**Разрешения для гостевых пользователей ограничены**: Эта политика определяет разрешения для гостей в вашем каталоге.</span><span class="sxs-lookup"><span data-stu-id="55d8f-127">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="55d8f-128">Выберите **Да** , чтобы заблокировать гостей от определенных задач в каталоге, например перечисление пользователей, групп и других ресурсов каталога.</span><span class="sxs-lookup"><span data-stu-id="55d8f-128">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="55d8f-129">Нажмите кнопку **нет** , чтобы предоставить гостям тот же доступ к данным каталога, что и обычные пользователи в вашем каталоге.</span><span class="sxs-lookup"><span data-stu-id="55d8f-129">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
     - <span data-ttu-id="55d8f-130">**Администраторы и пользователи в роли гостя могут пригласить**: чтобы разрешить администраторам и пользователям в роли "гость" приглашать гостей, установите для этого параметра политики значение **"Да**".</span><span class="sxs-lookup"><span data-stu-id="55d8f-130">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
     - <span data-ttu-id="55d8f-131">**Участники могут приглашать других пользователей**. Чтобы разрешить пользователям, не являющимся администраторами каталога, приглашать гостей, присвойте этой политике значение **Да** (рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="55d8f-131">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="55d8f-132">Если вы хотите, чтобы только администраторы могли добавлять гостей, можно присвоить этой политике значение **Нет**.</span><span class="sxs-lookup"><span data-stu-id="55d8f-132">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="55d8f-133">Имейте в виду, что присвоение значения **Нет** ограничит гостевое взаимодействие для владельцев команд, не являющихся администраторами. Они смогут добавлять только тех гостей Teams, которые уже добавлены администратором в AAD.</span><span class="sxs-lookup"><span data-stu-id="55d8f-133">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
     - <span data-ttu-id="55d8f-134">**Гости могут пригласить**гостей: чтобы разрешить гостям присоединиться к другим гостям, установите для этого параметра значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="55d8f-134">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="55d8f-135">В настоящее время в Teams не поддерживается роль приглашающего гостей, поэтому даже если вы установите для параметра **Гости могут приглашать** значение **Да**, гости не смогут приглашать других гостей в Teams.</span><span class="sxs-lookup"><span data-stu-id="55d8f-135">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
     - <span data-ttu-id="55d8f-136">**Включить одноразовый секретный код электронной почты для гостей (Предварительная версия)**: Дополнительные сведения о функции одноразового секретного кода можно найти в статье [Проверка подлинности по электронной почте (Предварительная версия)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span><span class="sxs-lookup"><span data-stu-id="55d8f-136">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
     - <span data-ttu-id="55d8f-137">**Ограничения для совместной работы**: Дополнительные сведения о том, как разрешить или заблокировать приглашения для конкретных доменов, можно найти в статье [разрешение и запрет на доступ к отдельным организациям для пользователей B2B](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="55d8f-137">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
        > [!NOTE]
        > <span data-ttu-id="55d8f-138">Для ограничений совместной работы ознакомьтесь со сведениями [Включение внешней совместной работы в сотрудничестве и управление пользователями, которые могут приглашать гостей](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="55d8f-138">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
    <span data-ttu-id="55d8f-139">Дополнительные сведения об управлении возможностью приглашения гостей см. в статье [Делегирование приглашений для службы совместной работы Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="55d8f-139">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="step-3-configure-office-365-groups"></a><span data-ttu-id="55d8f-140">Шаг 3: Настройка групп Office 365</span><span class="sxs-lookup"><span data-stu-id="55d8f-140">Step 3: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="55d8f-141">В центре администрирования Microsoft 365 **перейдите в** > раздел Параметры, выберите пункт **службы\*\*\*\*, а**затем — пункт **группы Office 365**.</span><span class="sxs-lookup"><span data-stu-id="55d8f-141">In the Microsoft 365 admin center, go to **Settings** > **Settings**, click **Services**, and then select **Office 365 Groups**.</span></span>

     ![Снимок экрана: параметры групп Office 365](media/guest-access-checklist-services-settings.png)
2. <span data-ttu-id="55d8f-143">Убедитесь, что флажок **let Members (группа) за пределами группы Access "доступ к Организации** " установлен.</span><span class="sxs-lookup"><span data-stu-id="55d8f-143">Make sure that the **Let group members outside the organization access group content** check box is selected.</span></span> <span data-ttu-id="55d8f-144">Если этот параметр не выбран, гости не смогут получать доступ к содержимому группы.</span><span class="sxs-lookup"><span data-stu-id="55d8f-144">If this setting is not selected, guests won't be able to access any group content.</span></span>

    ![Снимок экрана: параметры групп Office 365](media/guest-access-checklist-office365.png)
3. <span data-ttu-id="55d8f-146">Убедитесь, что установлен флажок **разрешить владельцам групп добавлять пользователей за пределами Организации в группы** .</span><span class="sxs-lookup"><span data-stu-id="55d8f-146">Make sure that the **Let group owners add people outside the organization to groups** check box is selected.</span></span> <span data-ttu-id="55d8f-147">Если этот параметр не установлен, владельцы групп не смогут добавлять новых гостей.</span><span class="sxs-lookup"><span data-stu-id="55d8f-147">If this setting is not selected, team owners won't be able to add new guests.</span></span> <span data-ttu-id="55d8f-148">Как минимум, этот параметр должен быть включен, чтобы поддерживать гостевой доступ.</span><span class="sxs-lookup"><span data-stu-id="55d8f-148">At a minimum, this setting must be on to support guest access.</span></span>

<span data-ttu-id="55d8f-149">Подробные инструкции по настройке этих параметров можно найти [в разделе Управление гостевым доступом в группах office 365](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) и [Управление гостевым доступом в группах Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="55d8f-149">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="55d8f-150">Шаг 4: Настройка общего использования в Office 365</span><span class="sxs-lookup"><span data-stu-id="55d8f-150">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="55d8f-151">Убедитесь в том, что пользователи могут добавлять гостей.</span><span class="sxs-lookup"><span data-stu-id="55d8f-151">Make sure that users can add guests.</span></span> <span data-ttu-id="55d8f-152">Вот как это можно делать:</span><span class="sxs-lookup"><span data-stu-id="55d8f-152">Here's how:</span></span>

1. <span data-ttu-id="55d8f-153">В\*\*\*\* центре администрирования Microsoft 365 **перейдите в** > раздел Параметры, нажмите кнопку **Безопасность & конфиденциальность**и выберите пункт **общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="55d8f-153">In the Microsoft 365 admin center, go to **Settings** > **Settings**, click **Security & privacy**, and then select **Sharing**.</span></span>

     ![На снимке экрана показан пример параметров служб](media/guest-access-checklist-security-privacy-settings.png)
 
2. <span data-ttu-id="55d8f-155">Установите флажок **Разрешить пользователям добавлять новых гостей для этой Организации** , а затем нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="55d8f-155">Select the **Let users add new guests to this organization** check box, and then click **Save changes**.</span></span>

     ![На снимке экрана показан пример переключателя "Параметры общего доступного"](media/guest-access-checklist-sharing-setting.png)
 
    > [!NOTE]
    > <span data-ttu-id="55d8f-157">Этот параметр эквивалентен пользователям в службах Azure AD, которые **могут приглашать** **пользователей** в параметрах **пользователя** > .</span><span class="sxs-lookup"><span data-stu-id="55d8f-157">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="55d8f-158">Шаг 5: Проверка параметров общего доступа в SharePoint</span><span class="sxs-lookup"><span data-stu-id="55d8f-158">Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="55d8f-159">Войдите в центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="55d8f-159">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="55d8f-160">В разделе **центры администрирования**выберите пункт **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="55d8f-160">Under **Admin centers**, select  **SharePoint**.</span></span>
3. <span data-ttu-id="55d8f-161">В новом центре администрирования SharePoint в разделе **сайты**выберите **активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="55d8f-161">In the new SharePoint admin center,  under **Sites**, select **Active sites**.</span></span>

    ![Активные сайты в центре администрирования SharePoint](media/guest-access-checklist-SPOSettings0.png)

3. <span data-ttu-id="55d8f-163">Выберите сайт и нажмите кнопку **общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="55d8f-163">Select the site, and then click **Sharing**.</span></span>
4. <span data-ttu-id="55d8f-164">Убедитесь в том, что для параметра задано значение " **кто угодно** " или " **новые" и "существующие гости**".</span><span class="sxs-lookup"><span data-stu-id="55d8f-164">Make sure that the option is set to **Anyone** or **New and existing guests**.</span></span>

     ![На снимке экрана показан пример переключателя параметров SharePoint Online](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="55d8f-166">Шаг 6: Настройка разрешений для гостевых пользователей</span><span class="sxs-lookup"><span data-stu-id="55d8f-166">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="55d8f-167">В приложении Teams на уровне отдельных групп Настройте разрешения гостя, определяющие, могут ли гости создавать, обновлять и удалять каналы.</span><span class="sxs-lookup"><span data-stu-id="55d8f-167">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="55d8f-168">Администраторы Teams, а также владельцы групп могут настраивать эти параметры.</span><span class="sxs-lookup"><span data-stu-id="55d8f-168">Teams admins as well as team owners can configure these settings.</span></span>

![Снимок экрана, на котором показан пример переключателя "Параметры группы/канала"](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="55d8f-170">Чтобы узнать больше о гостевом доступе, ознакомьтесь со статьей [гостевой доступ в Teams](guest-access.md) , [включите или отключите гостевой доступ к Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="55d8f-170">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="55d8f-171">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="55d8f-171">Troubleshooting</span></span>

<span data-ttu-id="55d8f-172">Если у вас возникли проблемы с настройкой гостевого доступа или добавлением гостей в Teams, воспользуйтесь приведенными ниже материалами.</span><span class="sxs-lookup"><span data-stu-id="55d8f-172">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="55d8f-173">Устранение неполадок с гостевым доступом в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55d8f-173">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="55d8f-174">Устранение неполадок в Teams</span><span class="sxs-lookup"><span data-stu-id="55d8f-174">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
