---
title: Контрольный список для гостевого доступа в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/25/2019
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
ms.openlocfilehash: 4ad6c0abba3b0ea85bdac7e2875369c4cd1d5150
ms.sourcegitcommit: 66213b972920b4e09faf7d7e732c4bfe7b322ac4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/21/2019
ms.locfileid: "35131419"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="f1d21-103">Контрольный список для гостевого доступа к Teams</span><span class="sxs-lookup"><span data-stu-id="f1d21-103">Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="f1d21-104">С помощью этого контрольного списка вы можете включить и настроить функцию гостевой доступа в Microsoft Teams в соответствии с настройками вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f1d21-104">Use this checklist to help you enable and configure the guest access feature in Microsoft Teams according to the preferences of your organization.</span></span>

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="f1d21-105">Общие сведения об ограничениях гостей</span><span class="sxs-lookup"><span data-stu-id="f1d21-105">Understand the limitations for guests</span></span>

<span data-ttu-id="f1d21-106">У гостей есть ограничения на проектирование.</span><span class="sxs-lookup"><span data-stu-id="f1d21-106">The guest experience has limitations by design.</span></span> <span data-ttu-id="f1d21-107">Убедитесь, что вы понимаете впечатление гостя, и вы не можете устранить проблему, которая не связана с проблемой.</span><span class="sxs-lookup"><span data-stu-id="f1d21-107">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="f1d21-108">Например, ниже приведен список некоторых функциональных возможностей, недоступных для гостей в Microsoft teams:</span><span class="sxs-lookup"><span data-stu-id="f1d21-108">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="f1d21-109">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="f1d21-109">OneDrive for Business</span></span>
- <span data-ttu-id="f1d21-110">Поиск людей за пределами Teams</span><span class="sxs-lookup"><span data-stu-id="f1d21-110">People search outside of Teams</span></span>
- <span data-ttu-id="f1d21-111">Календарь, запланированные собрания и сведения о собрании</span><span class="sxs-lookup"><span data-stu-id="f1d21-111">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="f1d21-112">ТСОП</span><span class="sxs-lookup"><span data-stu-id="f1d21-112">PSTN</span></span>
- <span data-ttu-id="f1d21-113">Организационная диаграмма</span><span class="sxs-lookup"><span data-stu-id="f1d21-113">Organization chart</span></span>
- <span data-ttu-id="f1d21-114">Создание и пересмотр команды</span><span class="sxs-lookup"><span data-stu-id="f1d21-114">Create or revise a team</span></span>
- <span data-ttu-id="f1d21-115">Поиск группы</span><span class="sxs-lookup"><span data-stu-id="f1d21-115">Browse for a team</span></span>
- <span data-ttu-id="f1d21-116">Отправка файлов в чат человека</span><span class="sxs-lookup"><span data-stu-id="f1d21-116">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="f1d21-117">Гости могут выполнять поиск и поиск пользователей за пределами группы, если они знают полный идентификатор электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f1d21-117">Guests can still search and find users, outside their team, if they know their full email ID.</span></span> <span data-ttu-id="f1d21-118">Чтобы не допустить этого, администраторы могут использовать шаблоны, такие как [Поиск](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) в каталогах с ограничениями, которые позволяют ограничить гостевые машины собственными ВИРТУАЛЬными глобальными адресными адресами.</span><span class="sxs-lookup"><span data-stu-id="f1d21-118">To prevent this, IT admins can use patterns like [scoped directory search](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) that have the ability to restrict Guests into their own virtual GAL.</span></span>

<span data-ttu-id="f1d21-119">Подробнее ознакомьтесь со сведениями о том, [как использовать гостевые возможности](guest-experience.md) и [гостевой доступ в группах Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="f1d21-119">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

### <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="f1d21-120">Гостевой доступ и внешний доступ (Федерация)</span><span class="sxs-lookup"><span data-stu-id="f1d21-120">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="f1d21-121">Если гости видят ошибки лицензий</span><span class="sxs-lookup"><span data-stu-id="f1d21-121">If your guests are seeing license errors</span></span>

<span data-ttu-id="f1d21-122">Гостевой доступ в Microsoft Teams использует Azure Active Directory Business to Business (B2B) и модель лицензирования.</span><span class="sxs-lookup"><span data-stu-id="f1d21-122">Guest access in Microsoft Teams uses Azure Active Directory Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="f1d21-123">Если вы видите ошибки лицензирования, ознакомьтесь с рекомендациями по [лицензированию B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) , чтобы понять требования к лицензированию пользователей организации, чтобы они могли пригласить гостей в организацию.</span><span class="sxs-lookup"><span data-stu-id="f1d21-123">If you’re seeing licensing errors, make sure to read the [B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to understand the licensing requirements your organization has so that your users are able to invite guests to your organization.</span></span>

<span data-ttu-id="f1d21-124">Вот несколько моментов, которые нужно помнить:</span><span class="sxs-lookup"><span data-stu-id="f1d21-124">A few things to remember:</span></span>

- <span data-ttu-id="f1d21-125">Для каждой платной лицензии на Azure Active Directory, назначенной пользователю, пользователи могут пригласить до пяти гостевых пользователей в рамках внешнего пользователя.</span><span class="sxs-lookup"><span data-stu-id="f1d21-125">For each paid Azure AD license that you assign to a user, your users can invite up to five guest users under the External User Allowance.</span></span>
- <span data-ttu-id="f1d21-126">Гости — это пользователи за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f1d21-126">Guests are users outside your organization.</span></span> <span data-ttu-id="f1d21-127">Ваши сотрудники, подрядчики на сайте, агенты по сайтам и т. д. нельзя добавить в качестве гостей.</span><span class="sxs-lookup"><span data-stu-id="f1d21-127">Your employees, onsite contractors, onsite agents, and so on can't be added as guests.</span></span> <span data-ttu-id="f1d21-128">То же касается ваших аффилированных лиц.</span><span class="sxs-lookup"><span data-stu-id="f1d21-128">The same applies to your affiliates.</span></span>
- <span data-ttu-id="f1d21-129">Гостевые лицензии подсчитываются с помощью приглашенной Организации.</span><span class="sxs-lookup"><span data-stu-id="f1d21-129">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="f1d21-130">Это следует помнить при расчете количества лицензий, которые вам понадобятся.</span><span class="sxs-lookup"><span data-stu-id="f1d21-130">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="f1d21-131">Лицензии будут учитываться в вашей организации, независимо от того, приходят ли приглашенные гости другим клиентам Office 365 или используют их личные адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f1d21-131">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a><span data-ttu-id="f1d21-132">□ Шаг 1: Настройка параметров в Azure AD Business-to-Business</span><span class="sxs-lookup"><span data-stu-id="f1d21-132">□  Step 1: Configure settings in Azure AD business-to-business</span></span>

1. <span data-ttu-id="f1d21-133">Вход в учетную записьhttps://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="f1d21-133">Sign in to https://portal.azure.com</span></span>
2. <span data-ttu-id="f1d21-134">На левой панели выберите **Azure Active Directory** .</span><span class="sxs-lookup"><span data-stu-id="f1d21-134">Click **Azure Active directory** in the left pane.</span></span>
3. <span data-ttu-id="f1d21-135">В разделе **Управление**выберите пункт **Параметры пользователя**.</span><span class="sxs-lookup"><span data-stu-id="f1d21-135">Under **Manage**, click **User settings**.</span></span>
4. <span data-ttu-id="f1d21-136">В разделе **внешние пользователи**выберите пункт **Управление внешними параметрами совместной работы**.</span><span class="sxs-lookup"><span data-stu-id="f1d21-136">Under **External users**, click **Manage External collaboration settings**.</span></span>
5. <span data-ttu-id="f1d21-137">На странице **внешние параметры совместной работы** убедитесь в том, что **Участники могут приглашать** установить значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="f1d21-137">On the **External collaboration settings** page make sure **Members can invite** is set to **Yes**.</span></span>

      ![<span data-ttu-id="f1d21-138">Снимок экрана, на котором показан пример переключателя параметров AAD.</span><span class="sxs-lookup"><span data-stu-id="f1d21-138">Screenshot shows an example of an AAD settings toggle.</span></span> ](media/guest-access-checklist-AADSettings1.png)

    <span data-ttu-id="f1d21-139">Для поддержки гостей **участникам может** быть присвоено значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="f1d21-139">To support guests, **Members can invite** must be set to **Yes**.</span></span> 
   
> [!NOTE] 
> <span data-ttu-id="f1d21-140">Если вы настроили **пользователей** на " **нет** ", а затем включите гостевой доступ в группах Office 365 и Microsoft Teams, администраторы могут управлять приглашениями гостей в каталог.</span><span class="sxs-lookup"><span data-stu-id="f1d21-140">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="f1d21-141">После того как гости находятся в каталоге, они могут быть добавлены в Teams участниками, которые являются владельцами групп.</span><span class="sxs-lookup"><span data-stu-id="f1d21-141">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span>

<span data-ttu-id="f1d21-142">Дополнительные сведения см. в статье [Авторизация гостевого доступа в Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="f1d21-142">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>


## <a name="-step-2-configure-office-365-groups"></a><span data-ttu-id="f1d21-143">□ Step 2: Настройка групп Office 365</span><span class="sxs-lookup"><span data-stu-id="f1d21-143">□ Step 2: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="f1d21-144">В центре администрирования Microsoft 365 перейдите в раздел службы **настройки** > **&** > **группы Office 365**.</span><span class="sxs-lookup"><span data-stu-id="f1d21-144">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="f1d21-145">Убедитесь в том **, что группа "разрешить участникам группы за пределами" содержимого группы "доступ к Организации"** имеет значение **вкл**.</span><span class="sxs-lookup"><span data-stu-id="f1d21-145">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="f1d21-146">Если этот параметр отключен, гости не смогут получать доступ к содержимому группы.</span><span class="sxs-lookup"><span data-stu-id="f1d21-146">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="f1d21-147">Убедитесь, что **владельцы групп смогут добавлять в группы пользователей за** пределами организации \*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="f1d21-147">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="f1d21-148">Если этот параметр отключен, владельцы групп не смогут добавлять новых гостей.</span><span class="sxs-lookup"><span data-stu-id="f1d21-148">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="f1d21-149">Как минимум, этот параметр должен быть включен, чтобы поддерживать гостевой доступ.</span><span class="sxs-lookup"><span data-stu-id="f1d21-149">At a minimum, this setting must be On to support guest access.</span></span>

     ![Снимок экрана: отображение групп Office 365](media/guest-access-checklist-office365.png)

<span data-ttu-id="f1d21-151">Подробные инструкции по настройке этих параметров можно найти [в статье Управление гостевым доступом в группах Office 365](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) и раздел "группы Office 365" для [авторизации гостевого доступа в Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="f1d21-151">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 groups](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and the section "Office 365 Groups" in [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="f1d21-152">□ Step 3: Включите гостевой доступ на уровне клиента</span><span class="sxs-lookup"><span data-stu-id="f1d21-152">□ Step 3: Enable guest access at the tenant level</span></span>

<span data-ttu-id="f1d21-153">Как минимум, необходимо включить гостевой доступ для Microsoft Teams в **центре администрирования Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="f1d21-153">At a minimum, you must turn on Guest access for Microsoft Teams under the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="f1d21-154">В центре администрирования Teams выберите\*\*\*\* **Параметры** > для всей Организации.</span><span class="sxs-lookup"><span data-stu-id="f1d21-154">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="f1d21-155">Установите переключатель **Разрешить гостевой доступ в Microsoft Teams** . \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f1d21-155">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Снимок экрана, на котором показан пример переключения параметров группы](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="f1d21-157">На этой же странице Настройте другие необходимые параметры гостя.</span><span class="sxs-lookup"><span data-stu-id="f1d21-157">On this same page, configure any other guest settings that you require.</span></span>
4. <span data-ttu-id="f1d21-158">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f1d21-158">Click **Save**.</span></span>

<span data-ttu-id="f1d21-159">Подробные инструкции можно найти [в разделе Включение и отключение гостевого доступа к Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="f1d21-159">For detailed instructions, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="--step-4-configure-sharing-in-office-365"></a><span data-ttu-id="f1d21-160">□ Действия 4: Настройка общего использования в Office 365</span><span class="sxs-lookup"><span data-stu-id="f1d21-160">□  Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="f1d21-161">Убедитесь в том, что пользователи могут добавлять гостей.</span><span class="sxs-lookup"><span data-stu-id="f1d21-161">Make sure that users can add guests.</span></span> <span data-ttu-id="f1d21-162">Вот как это можно делать:</span><span class="sxs-lookup"><span data-stu-id="f1d21-162">Here's how:</span></span>

1. <span data-ttu-id="f1d21-163">В центре администрирования Microsoft 365 выберите **Параметры** > **Безопасность & конфиденциальность**.</span><span class="sxs-lookup"><span data-stu-id="f1d21-163">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![На снимке экрана показан пример параметров служб](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="f1d21-165">В окне **общий доступ**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="f1d21-165">In **Sharing**, select **Edit**.</span></span>

     ![На снимке экрана показан пример переключателя "Параметры общего доступного"](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="f1d21-167">Установите переключатель **Разрешить пользователям добавлять новых гостей в эту организацию** , а затем нажмите кнопку **сохранить**. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f1d21-167">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![На снимке экрана показан пример переключателя "Параметры общего доступного"](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="f1d21-169">Этот параметр эквивалентен пользователям в службах Azure AD, которые **могут приглашать** **пользователей** в параметрах **пользователя** > .</span><span class="sxs-lookup"><span data-stu-id="f1d21-169">This setting is equivalent to the **Members can invite** setting in  **User settings** > **External users**  in Azure AD.</span></span>  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="f1d21-170">□ Шаг 5: Проверка параметров общего подключения в SharePoint</span><span class="sxs-lookup"><span data-stu-id="f1d21-170">□ Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="f1d21-171">Войдите в центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f1d21-171">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="f1d21-172">Выберите пункт **центр администрирования**, а затем — пункт **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="f1d21-172">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="f1d21-173">В центре администрирования SharePoint выберите **общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="f1d21-173">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="f1d21-174">Убедитесь, что *не* выбран параметр не **разрешать общий доступ за пределами Организации** .</span><span class="sxs-lookup"><span data-stu-id="f1d21-174">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![Снимок экрана, на котором показан пример переключателя "Параметры Спарепоинт Online".](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a><span data-ttu-id="f1d21-176">□ Шаг 6: включение определенных параметров каналов</span><span class="sxs-lookup"><span data-stu-id="f1d21-176">□ Step 6: Enable specific settings for channels</span></span> 

<span data-ttu-id="f1d21-177">В приложении Teams на уровне отдельных групп Настройте разрешения гостя таким образом, чтобы гости могли создавать, обновлять и удалять каналы.</span><span class="sxs-lookup"><span data-stu-id="f1d21-177">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="f1d21-178">В дополнение к администраторам, владельцы групп могут настроить этот параметр.</span><span class="sxs-lookup"><span data-stu-id="f1d21-178">In addition to admins,  team owners can configure this setting.</span></span>

![Снимок экрана, на котором показан пример переключателя "Параметры группы/канала"](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="f1d21-180">Дополнительные сведения, в том числе инструкции для видеороликов, можно найти [в разделе гостевой доступ в Microsoft Teams](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="f1d21-180">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="f1d21-181">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="f1d21-181">Troubleshooting</span></span>

<span data-ttu-id="f1d21-182">Если у вас возникли проблемы с добавлением гостей в Microsoft Teams, ознакомьтесь с [руководством по устранению неполадок с гостевым доступом](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span><span class="sxs-lookup"><span data-stu-id="f1d21-182">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


