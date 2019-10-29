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
ms.openlocfilehash: 04594f578d2375f69c38243251ee64506880d00e
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753324"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="b6cf0-103">Контрольный список для гостевого доступа в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b6cf0-103">Microsoft Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="b6cf0-104">С помощью этого контрольного списка вы можете включить и настроить гостевой доступ в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6cf0-105">Чтобы изменения вступили в силу, возможно, потребуется подождать до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-105">You may have to wait up to 24 hours for your changes to take effect.</span></span> 



## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="b6cf0-106">Действие 1: Включите гостевой доступ на уровне Организации в группе "Общие"</span><span class="sxs-lookup"><span data-stu-id="b6cf0-106">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="b6cf0-107">Чтобы включить гостевой доступ, перейдите в **центр администрирования Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-107">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="b6cf0-108">В центре администрирования Teams выберите > \*\*\*\* параметры для **всей Организации**.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-108">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="b6cf0-109">Установите переключатель **Разрешить гостевой доступ в Microsoft Teams** . \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b6cf0-109">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Снимок экрана, на котором показан пример переключения параметров группы](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="b6cf0-111">На этой же странице включите или отключите параметры **звонков**, **собраний**и **сообщений** для гостей.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-111">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="b6cf0-112">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-112">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="b6cf0-113">Если вы используете параметры по умолчанию в Azure Active Directory, SharePoint Online и групп Office 365, возможно, вы захотите настроить гостевой доступ.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-113">If you're using default settings in Azure Active Directory, SharePoint Online, and Office 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="b6cf0-114">В этом случае вы можете пропустить оставшиеся шаги.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-114">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="b6cf0-115">Если вы не уверены в том, что вы используете пользовательские параметры для AAD, SharePoint Online или групп Office 365, следуйте дальнейшим указаниям в этом контрольном списке.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-115">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Office 365 Groups, continue with the rest of the steps in this checklist.</span></span>


## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="b6cf0-116">Действие 2: Настройка параметров Azure AD для бизнеса-Бизнес</span><span class="sxs-lookup"><span data-stu-id="b6cf0-116">Step 2: Configure Azure AD business-to-business settings</span></span>

1. <span data-ttu-id="b6cf0-117">Войдите на [портал Azure](https://portal.azure.com) как администратор клиента.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-117">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="b6cf0-118">Выберите**Параметры пользователя**для**пользователей** >  **Azure Active Directory** > .</span><span class="sxs-lookup"><span data-stu-id="b6cf0-118">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="b6cf0-119">В разделе **внешние пользователи**выберите **Управление внешними параметрами совместной работы**.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-119">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="b6cf0-120">**Внешние параметры совместной работы** также доступны на странице " **организационные связи** ".</span><span class="sxs-lookup"><span data-stu-id="b6cf0-120">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="b6cf0-121">В службе Azure Active Directory в разделе **Управление**выберите пункт**Параметры** **организационных связей** > .</span><span class="sxs-lookup"><span data-stu-id="b6cf0-121">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="b6cf0-122">На странице **внешние параметры совместной работы** выберите политики, которые вы хотите включить.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-122">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

  - <span data-ttu-id="b6cf0-123">**Разрешения для гостевых пользователей ограничены**: Эта политика определяет разрешения для гостей в вашем каталоге.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-123">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="b6cf0-124">Выберите **Да** , чтобы заблокировать гостей от определенных задач в каталоге, например перечисление пользователей, групп и других ресурсов каталога.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-124">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="b6cf0-125">Нажмите кнопку **нет** , чтобы предоставить гостям тот же доступ к данным каталога, что и обычные пользователи в вашем каталоге.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-125">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
   - <span data-ttu-id="b6cf0-126">**Администраторы и пользователи в роли гостя могут пригласить**: чтобы разрешить администраторам и пользователям в роли "гость" приглашать гостей, установите для этого параметра политики значение **"Да**".</span><span class="sxs-lookup"><span data-stu-id="b6cf0-126">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="b6cf0-127">**Участники могут пригласить**пользователей, не являющихся администраторами вашего каталога, присоединиться к гостям и установить для этого параметра значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-127">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>
   
       > [!NOTE]
       > <span data-ttu-id="b6cf0-128">Если вы настроили **пользователей** на " **нет** ", а затем включите гостевой доступ в группах Office 365 и Microsoft Teams, администраторы могут управлять приглашениями гостей в каталог.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-128">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="b6cf0-129">После того как гости находятся в каталоге, они могут быть добавлены в Teams участниками, которые являются владельцами групп.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-129">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="b6cf0-130">Дополнительные сведения см. в статье [Авторизация гостевого доступа в Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="b6cf0-130">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
       > [!IMPORTANT]
       > <span data-ttu-id="b6cf0-131">Чтобы гостевой доступ мог работать на всех рабочих группах, вы должны настроить участников, чтобы они **могли пригласиться** в **"Да"**.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-131">For guest access to work at all in Teams, you must set **Members can invite** to **Yes**.</span></span>   
   - <span data-ttu-id="b6cf0-132">**Гости могут пригласить**гостей: чтобы разрешить гостям присоединиться к другим гостям, установите для этого параметра значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-132">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
       > [!IMPORTANT]
       > <span data-ttu-id="b6cf0-133">В настоящее время команды не поддерживают роль приглашенного гостя, поэтому даже если вы настроили **гостей** на **"Да"**, гости не смогут пригласить других гостей в Teams.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-133">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
   - <span data-ttu-id="b6cf0-134">**Включить одноразовый секретный код электронной почты для гостей (Предварительная версия)**: Дополнительные сведения о функции одноразового секретного кода можно найти в статье [Проверка подлинности по электронной почте (Предварительная версия)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span><span class="sxs-lookup"><span data-stu-id="b6cf0-134">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
   - <span data-ttu-id="b6cf0-135">**Ограничения для совместной работы**: Дополнительные сведения о том, как разрешить или заблокировать приглашения для конкретных доменов, можно найти в статье [разрешение и запрет на доступ к отдельным организациям для пользователей B2B](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="b6cf0-135">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
      > [!NOTE]
      > <span data-ttu-id="b6cf0-136">Для ограничений совместной работы ознакомьтесь со сведениями [Включение внешней совместной работы в сотрудничестве и управление пользователями, которые могут приглашать гостей](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="b6cf0-136">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
 
<span data-ttu-id="b6cf0-137">Дополнительные сведения об управлении возможностью приглашения гостей см. в статье [Делегирование приглашений для службы совместной работы Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="b6cf0-137">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>


## <a name="step-3-configure-office-365-groups"></a><span data-ttu-id="b6cf0-138">Шаг 3: Настройка групп Office 365</span><span class="sxs-lookup"><span data-stu-id="b6cf0-138">Step 3: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="b6cf0-139">В центре администрирования Microsoft 365 перейдите в раздел службы **настройки** > **&** > **группы Office 365**.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-139">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="b6cf0-140">Убедитесь в том **, что группа "разрешить участникам группы за пределами" содержимого группы "доступ к Организации"** имеет значение **вкл**.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-140">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="b6cf0-141">Если этот параметр отключен, гости не смогут получать доступ к содержимому группы.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-141">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="b6cf0-142">Убедитесь, что **владельцы групп смогут добавлять в группы пользователей за пределами Организации** **.**</span><span class="sxs-lookup"><span data-stu-id="b6cf0-142">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="b6cf0-143">Если этот параметр отключен, владельцы групп не смогут добавлять новых гостей.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-143">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="b6cf0-144">Как минимум, этот параметр должен быть включен, чтобы поддерживать гостевой доступ.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-144">At a minimum, this setting must be On to support guest access.</span></span>

     ![Снимок экрана: отображение групп Office 365](media/guest-access-checklist-office365.png)

<span data-ttu-id="b6cf0-146">Подробные инструкции по настройке этих параметров можно найти [в разделе Управление гостевым доступом в группах office 365](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) и [Управление гостевым доступом в группах Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="b6cf0-146">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="b6cf0-147">Шаг 4: Настройка общего использования в Office 365</span><span class="sxs-lookup"><span data-stu-id="b6cf0-147">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="b6cf0-148">Убедитесь в том, что пользователи могут добавлять гостей.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-148">Make sure that users can add guests.</span></span> <span data-ttu-id="b6cf0-149">Вот как это можно делать:</span><span class="sxs-lookup"><span data-stu-id="b6cf0-149">Here's how:</span></span>

1. <span data-ttu-id="b6cf0-150">В центре администрирования Microsoft 365 выберите **Параметры** > **Безопасность & конфиденциальность**.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-150">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![На снимке экрана показан пример параметров служб](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="b6cf0-152">В окне **общий доступ**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-152">In **Sharing**, select **Edit**.</span></span>

     ![На снимке экрана показан пример переключателя "Параметры общего доступного"](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="b6cf0-154">Установите переключатель **Разрешить пользователям добавлять новых гостей в эту организацию** **, а**затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-154">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![На снимке экрана показан пример переключателя "Параметры общего доступного"](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="b6cf0-156">Этот параметр эквивалентен пользователям в службах Azure AD, которые **могут приглашать** **пользователей** в параметрах **пользователя** > .</span><span class="sxs-lookup"><span data-stu-id="b6cf0-156">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  


## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="b6cf0-157">Шаг 5: Проверка параметров общего доступа в SharePoint</span><span class="sxs-lookup"><span data-stu-id="b6cf0-157">Step 5: Verify sharing setting in SharePoint</span></span>

<span data-ttu-id="b6cf0-158">Это и есть немного мозгового объявленияа.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-158">This one's a bit of a brain teaser.</span></span> <span data-ttu-id="b6cf0-159">Гостевой доступ в Teams не работает, если в центре администрирования SharePoint выбран параметр **не разрешать общий доступ за пределами Организации** .</span><span class="sxs-lookup"><span data-stu-id="b6cf0-159">Guest access in Teams doesn't work if the **Don't allow sharing outside your organization** setting is selected in the SharePoint admin center.</span></span>

1. <span data-ttu-id="b6cf0-160">Войдите в центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-160">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="b6cf0-161">Выберите пункт **центр администрирования**, а затем — пункт **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-161">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="b6cf0-162">В центре администрирования SharePoint выберите **общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-162">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="b6cf0-163">Убедитесь, что *не* выбран параметр не **разрешать общий доступ за пределами Организации** .</span><span class="sxs-lookup"><span data-stu-id="b6cf0-163">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![Снимок экрана, на котором показан пример переключателя "Параметры Спарепоинт Online".](media/guest-access-checklist-SPOSettings1.png)


## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="b6cf0-165">Шаг 6: Настройка разрешений для гостевых пользователей</span><span class="sxs-lookup"><span data-stu-id="b6cf0-165">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="b6cf0-166">В приложении Teams на уровне отдельных групп Настройте разрешения гостя, определяющие, могут ли гости создавать, обновлять и удалять каналы.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-166">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="b6cf0-167">Администраторы Teams, а также владельцы групп могут настраивать эти параметры.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-167">Teams admins as well as team owners can configure these settings.</span></span>

![Снимок экрана, на котором показан пример переключателя "Параметры группы/канала"](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="b6cf0-169">Чтобы узнать больше о гостевом доступе, ознакомьтесь со статьей [гостевой доступ в Teams](guest-access.md) , [включите или отключите гостевой доступ к Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="b6cf0-169">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="b6cf0-170">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="b6cf0-170">Troubleshooting</span></span>

<span data-ttu-id="b6cf0-171">Если у вас возникли проблемы с настройкой гостевого доступа или добавлением гостей в Teams, воспользуйтесь приведенными ниже материалами.</span><span class="sxs-lookup"><span data-stu-id="b6cf0-171">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="b6cf0-172">Устранение неполадок с гостевым доступом в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b6cf0-172">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="b6cf0-173">Устранение неполадок в Teams</span><span class="sxs-lookup"><span data-stu-id="b6cf0-173">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)



