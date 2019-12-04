---
title: Контрольный список для гостевого доступа в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: С помощью этого контрольного списка вы можете настроить гостевой доступ в Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bcba883166e01bd8a18d6d76b4622df0740500c8
ms.sourcegitcommit: 000fdb3bc1a0d4dda63fb00bab6a9a9ab0c85ab0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "39813779"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="8121f-103">Контрольный список для гостевого доступа в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8121f-103">Microsoft Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="8121f-104">С помощью этого контрольного списка вы можете включить и настроить гостевой доступ в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8121f-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span> <span data-ttu-id="8121f-105">Вы должны быть глобальным администратором или администратором Teams, чтобы внести эти изменения.</span><span class="sxs-lookup"><span data-stu-id="8121f-105">You need to be a Global Administrator or a Teams Administrator to make these changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8121f-106">Чтобы изменения вступили в силу, возможно, потребуется подождать до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="8121f-106">You may have to wait up to 24 hours for your changes to take effect.</span></span> 

<span data-ttu-id="8121f-107">В этом коротком видеоролике (5:31 минут) вы узнаете, как включить гостевой доступ в Microsoft 365, в том числе в Teams.</span><span class="sxs-lookup"><span data-stu-id="8121f-107">Watch this short video (5:31 minutes) to see how to turn on guest access throughout Microsoft 365, including Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]



## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="8121f-108">Действие 1: Включите гостевой доступ на уровне Организации в группе "Общие"</span><span class="sxs-lookup"><span data-stu-id="8121f-108">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="8121f-109">Чтобы включить гостевой доступ, перейдите в **центр администрирования Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="8121f-109">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="8121f-110">В центре администрирования Teams выберите > \*\*\*\* параметры для **всей Организации**.</span><span class="sxs-lookup"><span data-stu-id="8121f-110">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="8121f-111">Установите переключатель **Разрешить гостевой доступ в Microsoft Teams** . \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8121f-111">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Снимок экрана, на котором показан пример переключения параметров группы](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="8121f-113">На этой же странице включите или отключите параметры **звонков**, **собраний**и **сообщений** для гостей.</span><span class="sxs-lookup"><span data-stu-id="8121f-113">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="8121f-114">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8121f-114">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="8121f-115">Если вы используете параметры по умолчанию в Azure Active Directory, SharePoint Online и групп Office 365, возможно, вы захотите настроить гостевой доступ.</span><span class="sxs-lookup"><span data-stu-id="8121f-115">If you're using default settings in Azure Active Directory, SharePoint Online, and Office 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="8121f-116">В этом случае вы можете пропустить оставшиеся шаги.</span><span class="sxs-lookup"><span data-stu-id="8121f-116">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="8121f-117">Если вы не уверены в том, что вы используете пользовательские параметры для AAD, SharePoint Online или групп Office 365, следуйте дальнейшим указаниям в этом контрольном списке.</span><span class="sxs-lookup"><span data-stu-id="8121f-117">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Office 365 Groups, continue with the rest of the steps in this checklist.</span></span>


## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="8121f-118">Действие 2: Настройка параметров Azure AD для бизнеса-Бизнес</span><span class="sxs-lookup"><span data-stu-id="8121f-118">Step 2: Configure Azure AD business-to-business settings</span></span>

1. <span data-ttu-id="8121f-119">Войдите на [портал Azure](https://portal.azure.com) как администратор клиента.</span><span class="sxs-lookup"><span data-stu-id="8121f-119">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="8121f-120">Выберите**Параметры пользователя**для**пользователей** >  **Azure Active Directory** > .</span><span class="sxs-lookup"><span data-stu-id="8121f-120">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="8121f-121">В разделе **внешние пользователи**выберите **Управление внешними параметрами совместной работы**.</span><span class="sxs-lookup"><span data-stu-id="8121f-121">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="8121f-122">**Внешние параметры совместной работы** также доступны на странице " **организационные связи** ".</span><span class="sxs-lookup"><span data-stu-id="8121f-122">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="8121f-123">В службе Azure Active Directory в разделе **Управление**выберите пункт**Параметры** **организационных связей** > .</span><span class="sxs-lookup"><span data-stu-id="8121f-123">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="8121f-124">На странице **внешние параметры совместной работы** выберите политики, которые вы хотите включить.</span><span class="sxs-lookup"><span data-stu-id="8121f-124">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

    - <span data-ttu-id="8121f-125">**Разрешения для гостевых пользователей ограничены**: Эта политика определяет разрешения для гостей в вашем каталоге.</span><span class="sxs-lookup"><span data-stu-id="8121f-125">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="8121f-126">Выберите **Да** , чтобы заблокировать гостей от определенных задач в каталоге, например перечисление пользователей, групп и других ресурсов каталога.</span><span class="sxs-lookup"><span data-stu-id="8121f-126">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="8121f-127">Нажмите кнопку **нет** , чтобы предоставить гостям тот же доступ к данным каталога, что и обычные пользователи в вашем каталоге.</span><span class="sxs-lookup"><span data-stu-id="8121f-127">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
     - <span data-ttu-id="8121f-128">**Администраторы и пользователи в роли гостя могут пригласить**: чтобы разрешить администраторам и пользователям в роли "гость" приглашать гостей, установите для этого параметра политики значение **"Да**".</span><span class="sxs-lookup"><span data-stu-id="8121f-128">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
     - <span data-ttu-id="8121f-129">**Участники могут пригласить**пользователей, не являющихся администраторами вашего каталога, присоединиться к гостям и установить для этого параметра значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="8121f-129">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>

         > [!NOTE]
         > <span data-ttu-id="8121f-130">Если вы настроили **пользователей** на " **нет** ", а затем включите гостевой доступ в группах Office 365 и Microsoft Teams, администраторы могут управлять приглашениями гостей в каталог.</span><span class="sxs-lookup"><span data-stu-id="8121f-130">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="8121f-131">После того как гости находятся в каталоге, они могут быть добавлены в Teams участниками, которые являются владельцами групп.</span><span class="sxs-lookup"><span data-stu-id="8121f-131">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="8121f-132">Дополнительные сведения см. в статье [Авторизация гостевого доступа в Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="8121f-132">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="8121f-133">Чтобы обеспечить поддержку гостевого доступа в Teams, требуется установить для параметра **Участники могут приглашать** значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="8121f-133">For guest access to work at all in Teams, you must set **Members can invite** to **Yes**.</span></span>   
     - <span data-ttu-id="8121f-134">**Гости могут пригласить**гостей: чтобы разрешить гостям присоединиться к другим гостям, установите для этого параметра значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="8121f-134">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="8121f-135">В настоящее время в Teams не поддерживается роль приглашающего гостей, поэтому даже если вы установите для параметра **Гости могут приглашать** значение **Да**, гости не смогут приглашать других гостей в Teams.</span><span class="sxs-lookup"><span data-stu-id="8121f-135">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
     - <span data-ttu-id="8121f-136">**Включить одноразовый секретный код электронной почты для гостей (Предварительная версия)**: Дополнительные сведения о функции одноразового секретного кода можно найти в статье [Проверка подлинности по электронной почте (Предварительная версия)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span><span class="sxs-lookup"><span data-stu-id="8121f-136">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
     - <span data-ttu-id="8121f-137">**Ограничения для совместной работы**: Дополнительные сведения о том, как разрешить или заблокировать приглашения для конкретных доменов, можно найти в статье [разрешение и запрет на доступ к отдельным организациям для пользователей B2B](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="8121f-137">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
        > [!NOTE]
        > <span data-ttu-id="8121f-138">Для ограничений совместной работы ознакомьтесь со сведениями [Включение внешней совместной работы в сотрудничестве и управление пользователями, которые могут приглашать гостей](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="8121f-138">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
 
    <span data-ttu-id="8121f-139">Дополнительные сведения об управлении возможностью приглашения гостей см. в статье [Делегирование приглашений для службы совместной работы Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="8121f-139">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>


## <a name="step-3-configure-office-365-groups"></a><span data-ttu-id="8121f-140">Шаг 3: Настройка групп Office 365</span><span class="sxs-lookup"><span data-stu-id="8121f-140">Step 3: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="8121f-141">В центре администрирования Microsoft 365 перейдите в раздел службы **настройки** > **&** > **группы Office 365**.</span><span class="sxs-lookup"><span data-stu-id="8121f-141">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="8121f-142">Убедитесь в том **, что группа "разрешить участникам группы за пределами" содержимого группы "доступ к Организации"** имеет значение **вкл**.</span><span class="sxs-lookup"><span data-stu-id="8121f-142">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="8121f-143">Если этот параметр отключен, гости не смогут получать доступ к содержимому группы.</span><span class="sxs-lookup"><span data-stu-id="8121f-143">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="8121f-144">Убедитесь, что **владельцы групп смогут добавлять в группы пользователей за пределами Организации** **.**</span><span class="sxs-lookup"><span data-stu-id="8121f-144">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="8121f-145">Если этот параметр отключен, владельцы групп не смогут добавлять новых гостей.</span><span class="sxs-lookup"><span data-stu-id="8121f-145">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="8121f-146">Как минимум, этот параметр должен быть включен, чтобы поддерживать гостевой доступ.</span><span class="sxs-lookup"><span data-stu-id="8121f-146">At a minimum, this setting must be On to support guest access.</span></span>

     ![Снимок экрана: отображение групп Office 365](media/guest-access-checklist-office365.png)

<span data-ttu-id="8121f-148">Подробные инструкции по настройке этих параметров можно найти [в разделе Управление гостевым доступом в группах office 365](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) и [Управление гостевым доступом в группах Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="8121f-148">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="8121f-149">Шаг 4: Настройка общего использования в Office 365</span><span class="sxs-lookup"><span data-stu-id="8121f-149">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="8121f-150">Убедитесь в том, что пользователи могут добавлять гостей.</span><span class="sxs-lookup"><span data-stu-id="8121f-150">Make sure that users can add guests.</span></span> <span data-ttu-id="8121f-151">Вот как это можно делать:</span><span class="sxs-lookup"><span data-stu-id="8121f-151">Here's how:</span></span>

1. <span data-ttu-id="8121f-152">В центре администрирования Microsoft 365 выберите **Параметры** > **Безопасность & конфиденциальность**.</span><span class="sxs-lookup"><span data-stu-id="8121f-152">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![На снимке экрана показан пример параметров служб](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="8121f-154">В окне **общий доступ**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="8121f-154">In **Sharing**, select **Edit**.</span></span>

     ![На снимке экрана показан пример переключателя "Параметры общего доступного"](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="8121f-156">Установите переключатель **Разрешить пользователям добавлять новых гостей в эту организацию** **, а**затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8121f-156">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![На снимке экрана показан пример переключателя "Параметры общего доступного"](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
    > [!NOTE]
    > <span data-ttu-id="8121f-158">Этот параметр эквивалентен пользователям в службах Azure AD, которые **могут приглашать** **пользователей** в параметрах **пользователя** > .</span><span class="sxs-lookup"><span data-stu-id="8121f-158">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  


## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="8121f-159">Шаг 5: Проверка параметров общего доступа в SharePoint</span><span class="sxs-lookup"><span data-stu-id="8121f-159">Step 5: Verify sharing setting in SharePoint</span></span>

<span data-ttu-id="8121f-160">Это и есть немного мозгового объявленияа.</span><span class="sxs-lookup"><span data-stu-id="8121f-160">This one's a bit of a brain teaser.</span></span> <span data-ttu-id="8121f-161">Гостевой доступ в Teams не работает, если в центре администрирования SharePoint выбран параметр **не разрешать общий доступ за пределами Организации** .</span><span class="sxs-lookup"><span data-stu-id="8121f-161">Guest access in Teams doesn't work if the **Don't allow sharing outside your organization** setting is selected in the SharePoint admin center.</span></span>

1. <span data-ttu-id="8121f-162">Войдите в центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8121f-162">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="8121f-163">Выберите пункт **центр администрирования**, а затем — пункт **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="8121f-163">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="8121f-164">В центре администрирования SharePoint выберите **общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="8121f-164">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="8121f-165">Убедитесь, что *не* выбран параметр не **разрешать общий доступ за пределами Организации** .</span><span class="sxs-lookup"><span data-stu-id="8121f-165">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![Снимок экрана, на котором показан пример переключателя "Параметры Спарепоинт Online".](media/guest-access-checklist-SPOSettings1.png)


## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="8121f-167">Шаг 6: Настройка разрешений для гостевых пользователей</span><span class="sxs-lookup"><span data-stu-id="8121f-167">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="8121f-168">В приложении Teams на уровне отдельных групп Настройте разрешения гостя, определяющие, могут ли гости создавать, обновлять и удалять каналы.</span><span class="sxs-lookup"><span data-stu-id="8121f-168">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="8121f-169">Администраторы Teams, а также владельцы групп могут настраивать эти параметры.</span><span class="sxs-lookup"><span data-stu-id="8121f-169">Teams admins as well as team owners can configure these settings.</span></span>

![Снимок экрана, на котором показан пример переключателя "Параметры группы/канала"](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="8121f-171">Чтобы узнать больше о гостевом доступе, ознакомьтесь со статьей [гостевой доступ в Teams](guest-access.md) , [включите или отключите гостевой доступ к Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="8121f-171">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="8121f-172">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="8121f-172">Troubleshooting</span></span>

<span data-ttu-id="8121f-173">Если у вас возникли проблемы с настройкой гостевого доступа или добавлением гостей в Teams, воспользуйтесь приведенными ниже материалами.</span><span class="sxs-lookup"><span data-stu-id="8121f-173">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="8121f-174">Устранение неполадок с гостевым доступом в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8121f-174">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="8121f-175">Устранение неполадок в Teams</span><span class="sxs-lookup"><span data-stu-id="8121f-175">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)



