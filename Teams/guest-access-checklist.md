---
title: Контрольный список для гостевого доступа в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: С помощью этого контрольного списка вы можете настроить гостевой доступ в Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 09a6ec1f60ca4bfc39dbeb5ba1829330c3413560
ms.sourcegitcommit: a78fee3cad5b58bf41dd014a79f4316cf310c8d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2019
ms.locfileid: "35925360"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="f5c8e-103">Контрольный список для гостевого доступа к Teams</span><span class="sxs-lookup"><span data-stu-id="f5c8e-103">Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="f5c8e-104">С помощью этого контрольного списка вы можете включить и настроить функцию гостевой доступа в Microsoft Teams в соответствии с настройками вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-104">Use this checklist to help you enable and configure the guest access feature in Microsoft Teams according to the preferences of your organization.</span></span>

> [!NOTE] 
> <span data-ttu-id="f5c8e-105">Для ограничений совместной работы ознакомьтесь с разрешениями для [внешней совместной работы и управления пользователями, которые могут приглашать гостей](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="f5c8e-105">For collaboration restrictions see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="f5c8e-106">Общие сведения об ограничениях гостей</span><span class="sxs-lookup"><span data-stu-id="f5c8e-106">Understand the limitations for guests</span></span>

<span data-ttu-id="f5c8e-107">У гостей есть ограничения на проектирование.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-107">The guest experience has limitations by design.</span></span> <span data-ttu-id="f5c8e-108">Убедитесь, что вы понимаете впечатление гостя, и вы не можете устранить проблему, которая не связана с проблемой.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-108">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="f5c8e-109">Например, ниже приведен список некоторых функциональных возможностей, недоступных для гостей в Microsoft teams:</span><span class="sxs-lookup"><span data-stu-id="f5c8e-109">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="f5c8e-110">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="f5c8e-110">OneDrive for Business</span></span>
- <span data-ttu-id="f5c8e-111">Поиск людей за пределами Teams</span><span class="sxs-lookup"><span data-stu-id="f5c8e-111">People search outside of Teams</span></span>
- <span data-ttu-id="f5c8e-112">Календарь, запланированные собрания и сведения о собрании</span><span class="sxs-lookup"><span data-stu-id="f5c8e-112">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="f5c8e-113">ТСОП</span><span class="sxs-lookup"><span data-stu-id="f5c8e-113">PSTN</span></span>
- <span data-ttu-id="f5c8e-114">Организационная диаграмма</span><span class="sxs-lookup"><span data-stu-id="f5c8e-114">Organization chart</span></span>
- <span data-ttu-id="f5c8e-115">Создание и пересмотр команды</span><span class="sxs-lookup"><span data-stu-id="f5c8e-115">Create or revise a team</span></span>
- <span data-ttu-id="f5c8e-116">Поиск группы</span><span class="sxs-lookup"><span data-stu-id="f5c8e-116">Browse for a team</span></span>
- <span data-ttu-id="f5c8e-117">Отправка файлов в чат человека</span><span class="sxs-lookup"><span data-stu-id="f5c8e-117">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="f5c8e-118">Гости смогут искать и находить пользователей (за пределами группы), если они знают полный идентификатор электронной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-118">Guests can still search and find users (outside their team) if they know the user's full email ID.</span></span> <span data-ttu-id="f5c8e-119">Чтобы не допустить этого, администраторы могут использовать шаблоны, такие как [Поиск](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) в каталогах с ограничениями, которые позволяют ограничить гостевые машины собственными ВИРТУАЛЬными глобальными адресными адресами.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-119">To prevent this, IT admins can use patterns like [scoped directory search](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) that have the ability to restrict Guests into their own virtual GAL.</span></span>

<span data-ttu-id="f5c8e-120">Подробнее ознакомьтесь со сведениями о том, [как использовать гостевые возможности](guest-experience.md) и [гостевой доступ в группах Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="f5c8e-120">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

### <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="f5c8e-121">Гостевой доступ и внешний доступ (Федерация)</span><span class="sxs-lookup"><span data-stu-id="f5c8e-121">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

> [!NOTE] 
> <span data-ttu-id="f5c8e-122">В настоящее время в Microsoft Teams не поддерживается роль участника гостя.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-122">Currently, Microsoft Teams does not support the guest inviter role.</span></span> <span data-ttu-id="f5c8e-123">По крайней мере для переключателя "участники могут пригласить" необходимо установить значение "Да" для гостевого доступа к работе в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-123">At a minimum the "members can invite" toggle must be set to "Yes" for guest access to work in Microsoft Teams.</span></span> <span data-ttu-id="f5c8e-124">Если вы настроили "нет", а затем включите гостевой доступ в группах Office 365 и Microsoft Teams, администраторы могут управлять приглашениями гостей в каталог.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-124">If you set "members can invite" to "No" and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="f5c8e-125">После того как гости находятся в каталоге, они могут быть добавлены в Teams участниками, которые являются владельцами групп.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-125">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="f5c8e-126">Если гости видят ошибки лицензий</span><span class="sxs-lookup"><span data-stu-id="f5c8e-126">If your guests are seeing license errors</span></span>

<span data-ttu-id="f5c8e-127">Гостевой доступ в Microsoft Teams использует службу Azure Active Directory (Azure AD) для бизнеса (B2B) и модель лицензирования.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-127">Guest access in Microsoft Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="f5c8e-128">Если вы видите ошибки лицензирования, ознакомьтесь с рекомендациями по [лицензированию B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) , чтобы понять требования к лицензированию пользователей организации, чтобы они могли пригласить гостей в организацию.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-128">If you’re seeing licensing errors, make sure to read the [B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to understand the licensing requirements your organization has so that your users are able to invite guests to your organization.</span></span>

<span data-ttu-id="f5c8e-129">Вот несколько моментов, которые нужно помнить:</span><span class="sxs-lookup"><span data-stu-id="f5c8e-129">A few things to remember:</span></span>

- <span data-ttu-id="f5c8e-130">Гости — это пользователи за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-130">Guests are users outside your organization.</span></span> <span data-ttu-id="f5c8e-131">Ваши сотрудники, подрядчики на сайте, агенты по сайтам и т. д. нельзя добавить в качестве гостей.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-131">Your employees, onsite contractors, onsite agents, and so on can't be added as guests.</span></span> <span data-ttu-id="f5c8e-132">То же касается ваших аффилированных лиц.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-132">The same applies to your affiliates.</span></span>
- <span data-ttu-id="f5c8e-133">Гостевые лицензии подсчитываются с помощью приглашенной Организации.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-133">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="f5c8e-134">Это следует помнить при расчете количества лицензий, которые вам понадобятся.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-134">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="f5c8e-135">Лицензии будут учитываться в вашей организации, независимо от того, приходят ли приглашенные гости другим клиентам Office 365 или используют их личные адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-135">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a><span data-ttu-id="f5c8e-136">□ Шаг 1: Настройка параметров в Azure AD Business-to-Business</span><span class="sxs-lookup"><span data-stu-id="f5c8e-136">□  Step 1: Configure settings in Azure AD business-to-business</span></span>

1. <span data-ttu-id="f5c8e-137">Войдите на [портал Azure](https://portal.azure.com) как администратор клиента.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-137">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="f5c8e-138">Выберите**Параметры пользователя**для**пользователей** >  **Azure Active Directory** > .</span><span class="sxs-lookup"><span data-stu-id="f5c8e-138">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="f5c8e-139">В разделе **внешние пользователи**выберите **Управление внешними параметрами совместной работы**.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-139">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="f5c8e-140">**Внешние параметры совместной работы** также доступны на странице " **организационные связи** ".</span><span class="sxs-lookup"><span data-stu-id="f5c8e-140">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="f5c8e-141">В службе Azure Active Directory в разделе **Управление**выберите пункт \*\*\*\* > **Параметры**организационных связей.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-141">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="f5c8e-142">На странице **внешние параметры совместной работы** выберите политики, которые вы хотите включить.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-142">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

  - <span data-ttu-id="f5c8e-143">**Разрешения для гостевых пользователей ограничены**: Эта политика определяет разрешения для гостей в вашем каталоге.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-143">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="f5c8e-144">Выберите **Да** , чтобы заблокировать гостей от определенных задач в каталоге, например перечисление пользователей, групп и других ресурсов каталога.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-144">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="f5c8e-145">Нажмите кнопку **нет** , чтобы предоставить гостям тот же доступ к данным каталога, что и обычные пользователи в вашем каталоге.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-145">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
   - <span data-ttu-id="f5c8e-146">**Администраторы и пользователи в роли гостя могут пригласить**: чтобы разрешить администраторам и пользователям в роли "гость" приглашать гостей, установите для этого параметра политики значение **"Да**".</span><span class="sxs-lookup"><span data-stu-id="f5c8e-146">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="f5c8e-147">**Участники могут пригласить**пользователей, не являющихся администраторами вашего каталога, присоединиться к гостям и установить для этого параметра значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-147">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>
   
       > [!NOTE]
       > <span data-ttu-id="f5c8e-148">Если вы настроили **пользователей** на " **нет** ", а затем включите гостевой доступ в группах Office 365 и Microsoft Teams, администраторы могут управлять приглашениями гостей в каталог.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-148">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="f5c8e-149">После того как гости находятся в каталоге, они могут быть добавлены в Teams участниками, которые являются владельцами групп.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-149">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="f5c8e-150">Дополнительные сведения см. в статье [Авторизация гостевого доступа в Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="f5c8e-150">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
   
   - <span data-ttu-id="f5c8e-151">**Гости могут пригласить**гостей: чтобы разрешить гостям присоединиться к другим гостям, установите для этого параметра значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-151">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="f5c8e-152">**Включить одноразовый секретный код электронной почты для гостей (Предварительная версия)**: Дополнительные сведения о функции одноразового секретного кода можно найти в статье [Проверка подлинности по электронной почте (Предварительная версия)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span><span class="sxs-lookup"><span data-stu-id="f5c8e-152">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
   - <span data-ttu-id="f5c8e-153">**Ограничения для совместной работы**: Дополнительные сведения о том, как разрешить или заблокировать приглашения для конкретных доменов, можно найти в статье [разрешение и запрет на доступ к отдельным организациям для пользователей B2B](allow-deny-list.md).</span><span class="sxs-lookup"><span data-stu-id="f5c8e-153">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](allow-deny-list.md).</span></span>

## <a name="-step-2-configure-office-365-groups"></a><span data-ttu-id="f5c8e-154">□ Step 2: Настройка групп Office 365</span><span class="sxs-lookup"><span data-stu-id="f5c8e-154">□ Step 2: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="f5c8e-155">В центре администрирования Microsoft 365 перейдите в раздел службы **настройки** > **&** > **группы Office 365**.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-155">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="f5c8e-156">Убедитесь в том **, что группа "разрешить участникам группы за пределами" содержимого группы "доступ к Организации"** имеет значение **вкл**.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-156">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="f5c8e-157">Если этот параметр отключен, гости не смогут получать доступ к содержимому группы.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-157">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="f5c8e-158">Убедитесь, что **владельцы групп смогут добавлять в группы пользователей за** пределами организации \*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-158">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="f5c8e-159">Если этот параметр отключен, владельцы групп не смогут добавлять новых гостей.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-159">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="f5c8e-160">Как минимум, этот параметр должен быть включен, чтобы поддерживать гостевой доступ.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-160">At a minimum, this setting must be On to support guest access.</span></span>

     ![Снимок экрана: отображение групп Office 365](media/guest-access-checklist-office365.png)

<span data-ttu-id="f5c8e-162">Подробные инструкции по настройке этих параметров можно найти [в разделе Управление гостевым доступом в группах office 365](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) и [Управление гостевым доступом в группах Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="f5c8e-162">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="f5c8e-163">□ Step 3: Включите гостевой доступ на уровне клиента</span><span class="sxs-lookup"><span data-stu-id="f5c8e-163">□ Step 3: Enable guest access at the tenant level</span></span>

<span data-ttu-id="f5c8e-164">Как минимум, необходимо включить гостевой доступ для Microsoft Teams в **центре администрирования Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-164">At a minimum, you must turn on guest access for Microsoft Teams under the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="f5c8e-165">В центре администрирования Teams выберите\*\*\*\* **Параметры** > для всей Организации.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-165">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="f5c8e-166">Установите переключатель **Разрешить гостевой доступ в Microsoft Teams** . \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f5c8e-166">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Снимок экрана, на котором показан пример переключения параметров группы](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="f5c8e-168">На этой же странице Настройте другие необходимые параметры гостя.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-168">On this same page, configure any other guest settings that you require.</span></span>
4. <span data-ttu-id="f5c8e-169">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-169">Click **Save**.</span></span>

<span data-ttu-id="f5c8e-170">Подробные инструкции можно найти в разделе [Включение и отключение гостевого доступа к Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="f5c8e-170">For detailed instructions, see [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="--step-4-configure-sharing-in-office-365"></a><span data-ttu-id="f5c8e-171">□ Действия 4: Настройка общего использования в Office 365</span><span class="sxs-lookup"><span data-stu-id="f5c8e-171">□  Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="f5c8e-172">Убедитесь в том, что пользователи могут добавлять гостей.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-172">Make sure that users can add guests.</span></span> <span data-ttu-id="f5c8e-173">Вот как это можно делать:</span><span class="sxs-lookup"><span data-stu-id="f5c8e-173">Here's how:</span></span>

1. <span data-ttu-id="f5c8e-174">В центре администрирования Microsoft 365 выберите **Параметры** > **Безопасность & конфиденциальность**.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-174">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![На снимке экрана показан пример параметров служб](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="f5c8e-176">В окне **общий доступ**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-176">In **Sharing**, select **Edit**.</span></span>

     ![На снимке экрана показан пример переключателя "Параметры общего доступного"](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="f5c8e-178">Установите переключатель **Разрешить пользователям добавлять новых гостей в эту организацию** , а затем нажмите кнопку **сохранить**. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f5c8e-178">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![На снимке экрана показан пример переключателя "Параметры общего доступного"](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="f5c8e-180">Этот параметр эквивалентен пользователям в службах Azure AD, которые **могут приглашать** **пользователей** в параметрах **пользователя** > .</span><span class="sxs-lookup"><span data-stu-id="f5c8e-180">This setting is equivalent to the **Members can invite** setting in  **User settings** > **External users**  in Azure AD.</span></span>  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="f5c8e-181">□ Шаг 5: Проверка параметров общего подключения в SharePoint</span><span class="sxs-lookup"><span data-stu-id="f5c8e-181">□ Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="f5c8e-182">Войдите в центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-182">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="f5c8e-183">Выберите пункт **центр администрирования**, а затем — пункт **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-183">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="f5c8e-184">В центре администрирования SharePoint выберите **общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-184">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="f5c8e-185">Убедитесь, что *не* выбран параметр не **разрешать общий доступ за пределами Организации** .</span><span class="sxs-lookup"><span data-stu-id="f5c8e-185">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![Снимок экрана, на котором показан пример переключателя "Параметры Спарепоинт Online".](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a><span data-ttu-id="f5c8e-187">□ Шаг 6: включение определенных параметров каналов</span><span class="sxs-lookup"><span data-stu-id="f5c8e-187">□ Step 6: Enable specific settings for channels</span></span> 

<span data-ttu-id="f5c8e-188">В приложении Teams на уровне отдельных групп Настройте разрешения гостя таким образом, чтобы гости могли создавать, обновлять и удалять каналы.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-188">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="f5c8e-189">В дополнение к администраторам, владельцы групп могут настроить этот параметр.</span><span class="sxs-lookup"><span data-stu-id="f5c8e-189">In addition to admins,  team owners can configure this setting.</span></span>

![Снимок экрана, на котором показан пример переключателя "Параметры группы/канала"](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="f5c8e-191">Дополнительные сведения, в том числе инструкции для видеороликов, можно найти [в разделе гостевой доступ в Microsoft Teams](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="f5c8e-191">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="f5c8e-192">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="f5c8e-192">Troubleshooting</span></span>

<span data-ttu-id="f5c8e-193">Если у вас возникли проблемы с добавлением гостей в Microsoft Teams, ознакомьтесь с [руководством по устранению неполадок с гостевым доступом](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span><span class="sxs-lookup"><span data-stu-id="f5c8e-193">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


