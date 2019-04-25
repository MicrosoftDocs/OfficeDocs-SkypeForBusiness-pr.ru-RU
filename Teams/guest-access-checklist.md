---
title: Контрольный список для гостевого доступа в Microsoft Teams
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 03/25/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: Используйте этот контрольный список для настройки доступа гостя в группах Microsoft.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 68beeba403f6a64e194594d5bd40b985c8051dc6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32237550"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="73a91-103">Контрольный список доступа гостевой группы</span><span class="sxs-lookup"><span data-stu-id="73a91-103">Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="73a91-104">Используйте этот контрольный список для включения и настройки компонента гостевой доступ в группах Microsoft в соответствии с предпочтениями вашей организации.</span><span class="sxs-lookup"><span data-stu-id="73a91-104">Use this checklist to help you enable and configure the guest access feature in Microsoft Teams according to the preferences of your organization.</span></span>

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="73a91-105">Ознакомиться с ограничениями по Гости</span><span class="sxs-lookup"><span data-stu-id="73a91-105">Understand the limitations for guests</span></span>

<span data-ttu-id="73a91-106">На взаимодействие с гостем имеет ограничения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="73a91-106">The guest experience has limitations by design.</span></span> <span data-ttu-id="73a91-107">Убедитесь, что изучить гостевой качества, чтобы не пытайтесь исправление, не является источником проблем.</span><span class="sxs-lookup"><span data-stu-id="73a91-107">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="73a91-108">Далее представлен список некоторых функциональных возможностей, которые недоступен Гость группами Майкрософт, например:</span><span class="sxs-lookup"><span data-stu-id="73a91-108">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="73a91-109">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="73a91-109">OneDrive for Business</span></span>
- <span data-ttu-id="73a91-110">Поиск людей не из группы</span><span class="sxs-lookup"><span data-stu-id="73a91-110">People search outside of Teams</span></span>
- <span data-ttu-id="73a91-111">Календарь, запланированные собрания или сведения о собрании</span><span class="sxs-lookup"><span data-stu-id="73a91-111">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="73a91-112">ТСОП</span><span class="sxs-lookup"><span data-stu-id="73a91-112">PSTN</span></span>
- <span data-ttu-id="73a91-113">Организационная диаграмма</span><span class="sxs-lookup"><span data-stu-id="73a91-113">Organization chart</span></span>
- <span data-ttu-id="73a91-114">Создание или изменение группы</span><span class="sxs-lookup"><span data-stu-id="73a91-114">Create or revise a team</span></span>
- <span data-ttu-id="73a91-115">Поиск группы</span><span class="sxs-lookup"><span data-stu-id="73a91-115">Browse for a team</span></span>
- <span data-ttu-id="73a91-116">Передача файлов между двумя пользователями чата</span><span class="sxs-lookup"><span data-stu-id="73a91-116">Upload files to a person-to-person chat</span></span>

<span data-ttu-id="73a91-117">Для получения дополнительных сведений см [возможности взаимодействия гостя](guest-experience.md) и [гостевой доступ в группах Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="73a91-117">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

### <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="73a91-118">Доступ в качестве гостя и внешнего доступа (федерации)</span><span class="sxs-lookup"><span data-stu-id="73a91-118">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="73a91-119">Если Гости видите ошибки лицензии</span><span class="sxs-lookup"><span data-stu-id="73a91-119">If your guests are seeing license errors</span></span>

<span data-ttu-id="73a91-120">Гостевой доступ в группах Майкрософт использует Azure Active Directory бизнеса к компании (B2B) и его модели лицензирования.</span><span class="sxs-lookup"><span data-stu-id="73a91-120">Guest access in Microsoft Teams uses Azure Active Directory Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="73a91-121">Если вы видите лицензирования ошибки, обязательно прочтите руководство лицензирования B2B понять условия лицензионного соглашения, которыми вашей организации, чтобы пользователи могли приглашать Гости для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="73a91-121">If you’re seeing licensing errors, make sure to read the B2B licensing guidance to understand the licensing requirements your organization has so that your users are able to invite guests to your organization.</span></span>

<span data-ttu-id="73a91-122">Следует помнить нескольких моментах:</span><span class="sxs-lookup"><span data-stu-id="73a91-122">A few things to remember:</span></span>

- <span data-ttu-id="73a91-123">Для каждого платных лицензии Azure AD, назначение пользователю, пользователей можно пригласить до пяти гости в разделе внешние льгот пользователя.</span><span class="sxs-lookup"><span data-stu-id="73a91-123">For each paid Azure AD license that you assign to a user, your users can invite up to five guest users under the External User Allowance.</span></span>
- <span data-ttu-id="73a91-124">Гости являются пользователей за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="73a91-124">Guests are users outside your organization.</span></span> <span data-ttu-id="73a91-125">Как гости нельзя добавить сотрудников, подрядчиков на сайте, на сайте агентов и т. д.</span><span class="sxs-lookup"><span data-stu-id="73a91-125">Your employees, onsite contractors, onsite agents, and so on can't be added as guests.</span></span> <span data-ttu-id="73a91-126">То же самое применяется к вашей дочерних компаний.</span><span class="sxs-lookup"><span data-stu-id="73a91-126">The same applies to your affiliates.</span></span>
- <span data-ttu-id="73a91-127">Гостевая количество лицензий удваивается по приглашению организации.</span><span class="sxs-lookup"><span data-stu-id="73a91-127">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="73a91-128">Это необходимо учитывайте при расчете число лицензий, необходимые.</span><span class="sxs-lookup"><span data-stu-id="73a91-128">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="73a91-129">Количество лицензий удваивается с вашей организацией или приглашенным потребуется поступают из другого клиента Office 365 с помощью их адресов электронной почты личные.</span><span class="sxs-lookup"><span data-stu-id="73a91-129">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a><span data-ttu-id="73a91-130">□ Шаг 1: Настройка параметров в business Azure AD-бизнес</span><span class="sxs-lookup"><span data-stu-id="73a91-130">□  Step 1: Configure settings in Azure AD business-to-business</span></span>

1. <span data-ttu-id="73a91-131">Войдите в https://portal.azure.com.</span><span class="sxs-lookup"><span data-stu-id="73a91-131">Sign in to https://portal.azure.com.</span></span>
2. <span data-ttu-id="73a91-132">В левой области щелкните **Azure Active directory** .</span><span class="sxs-lookup"><span data-stu-id="73a91-132">Click **Azure Active directory** in the left pane.</span></span>
3. <span data-ttu-id="73a91-133">В разделе **Управление**щелкните **Параметры пользователя**.</span><span class="sxs-lookup"><span data-stu-id="73a91-133">Under **Manage**, click **User settings**.</span></span>
4. <span data-ttu-id="73a91-134">В разделе **внешние пользователи**щелкните **Управление внешние параметры совместной работы**.</span><span class="sxs-lookup"><span data-stu-id="73a91-134">Under **External users**, click **Manage External collaboration settings**.</span></span>
5. <span data-ttu-id="73a91-135">На странице **параметров внешней совместной работы** убедитесь, что **можно пригласить участников** задано значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="73a91-135">On the **External collaboration settings** page make sure **Members can invite** is set to **Yes**.</span></span>

      ![<span data-ttu-id="73a91-136">Снимок экрана показан пример AAD параметры переключателя.</span><span class="sxs-lookup"><span data-stu-id="73a91-136">Screenshot shows an example of an AAD settings toggle.</span></span> ](media/guest-access-checklist-AADSettings1.png)

    <span data-ttu-id="73a91-137">Для поддержки Гости, **можно пригласить участников** должен иметь значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="73a91-137">To support guests, **Members can invite** must be set to **Yes**.</span></span> 
   
> [!NOTE] 
> <span data-ttu-id="73a91-138">Если значение **можно пригласить участников** **Нет** и затем включить гостевого доступа в Office 365 групп и группами Майкрософт, администраторы могут управлять гостевой приглашения в каталоге.</span><span class="sxs-lookup"><span data-stu-id="73a91-138">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="73a91-139">После Гости находятся в каталоге, они могут добавляться к группам участниками без прав администратора, которые владельцы сайтов группы.</span><span class="sxs-lookup"><span data-stu-id="73a91-139">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span>

<span data-ttu-id="73a91-140">Дополнительные сведения см. в статье [Авторизация гостевого доступа в Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="73a91-140">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>


## <a name="-step-2-configure-office-365-groups"></a><span data-ttu-id="73a91-141">□ Шаг 2: Настройка Office 365 групп</span><span class="sxs-lookup"><span data-stu-id="73a91-141">□ Step 2: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="73a91-142">В центре администрирования Microsoft 365 перейдите в раздел **Параметры** > **& служб надстройки** > **Группы Office 365**.</span><span class="sxs-lookup"><span data-stu-id="73a91-142">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="73a91-143">Убедитесь в том, что **члены группы за пределами содержимого группе организации клиента** — это значение **на**.</span><span class="sxs-lookup"><span data-stu-id="73a91-143">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="73a91-144">Если этот параметр отключен, Гости не сможет получить доступ к содержимому любой группы.</span><span class="sxs-lookup"><span data-stu-id="73a91-144">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="73a91-145">Убедитесь в том, что **позволить добавлять пользователей за пределами организации, чтобы группы владельцев группы** — это значение **на**.</span><span class="sxs-lookup"><span data-stu-id="73a91-145">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="73a91-146">Если этот параметр отключен, владельцев группы не сможет для добавления нового Гости.</span><span class="sxs-lookup"><span data-stu-id="73a91-146">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="73a91-147">Как минимум этот параметр должен быть вход в систему поддержки доступа.</span><span class="sxs-lookup"><span data-stu-id="73a91-147">At a minimum, this setting must be On to support guest access.</span></span>

     ![Снимок экрана показана переключение группы Office 365](media/guest-access-checklist-office365.png)

<span data-ttu-id="73a91-149">Подробные инструкции по настройке этих параметров в разделе [Управление доступом гостевой в Office 365 групп](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) и раздел «Группы Office 365» в [access гостевой авторизовать в группах Microsoft](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="73a91-149">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 groups](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and the section "Office 365 Groups" in [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="73a91-150">□ Шаг 3: Включение гостевого доступа на уровне клиента</span><span class="sxs-lookup"><span data-stu-id="73a91-150">□ Step 3: Enable guest access at the tenant level</span></span>

<span data-ttu-id="73a91-151">Как минимум необходимо включить доступ в качестве гостя для групп Майкрософт в разделе **группами Майкрософт центра администрирования**.</span><span class="sxs-lookup"><span data-stu-id="73a91-151">At a minimum, you must turn on Guest access for Microsoft Teams under the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="73a91-152">В центре администрирования группы выберите **Параметры масштабе организации** > **доступ в качестве гостя**.</span><span class="sxs-lookup"><span data-stu-id="73a91-152">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="73a91-153">Установка параметра **Разрешить доступ гостя в группах Майкрософт** для **на**.</span><span class="sxs-lookup"><span data-stu-id="73a91-153">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Снимок экрана показан пример переключатель параметров группы](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="73a91-155">На этой же странице настройте другие необходимые параметры гостя.</span><span class="sxs-lookup"><span data-stu-id="73a91-155">On this same page, configure any other guest settings that you require.</span></span>
4. <span data-ttu-id="73a91-156">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="73a91-156">Click **Save**.</span></span>

<span data-ttu-id="73a91-157">Подробные инструкции в разделе [Включение и отключение гостевой доступ к группами Майкрософт](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="73a91-157">For detailed instructions, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="--step-4-configure-sharing-in-office-365"></a><span data-ttu-id="73a91-158">□ Шаг 4: Настройка общего доступа в Office 365</span><span class="sxs-lookup"><span data-stu-id="73a91-158">□  Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="73a91-159">Убедитесь в том, что пользователи могут добавлять Гости.</span><span class="sxs-lookup"><span data-stu-id="73a91-159">Make sure that users can add guests.</span></span> <span data-ttu-id="73a91-160">Вот как:</span><span class="sxs-lookup"><span data-stu-id="73a91-160">Here's how:</span></span>

1. <span data-ttu-id="73a91-161">В центре администрирования Microsoft 365 перейдите в раздел **Параметры** > **конфиденциальности & безопасности**.</span><span class="sxs-lookup"><span data-stu-id="73a91-161">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![Снимок экрана показан пример параметры служб](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="73a91-163">В **общий доступ**выберите команду **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="73a91-163">In **Sharing**, select **Edit**.</span></span>

     ![Снимок экрана показан пример общего доступа переключателя параметров](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="73a91-165">Значение **Пользователи могут добавлять новые Гости к данной организации** **на**и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="73a91-165">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![Снимок экрана показан пример общего доступа переключателя параметров](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="73a91-167">Этот параметр эквивалентен параметру **можно пригласить участников** в **пользовательских параметров**для > **внешних пользователей** в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="73a91-167">This setting is equivalent to the **Members can invite** setting in  **User settings** > **External users**  in Azure AD.</span></span>  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="73a91-168">□ Этап 5: проверка общего доступа, заданное в SharePoint</span><span class="sxs-lookup"><span data-stu-id="73a91-168">□ Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="73a91-169">Войдите в Центр администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="73a91-169">Sign in to the Office 365 admin center.</span></span>
2. <span data-ttu-id="73a91-170">Щелкните **Центр администрирования**, а затем выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="73a91-170">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="73a91-171">В центре администрирования SharePoint выберите параметр **общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="73a91-171">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="73a91-172">Убедитесь, что параметр для **не разрешать общий доступ к за пределами организации** *не* установлен.</span><span class="sxs-lookup"><span data-stu-id="73a91-172">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![Снимок экрана показан пример SparePoint Online параметры переключателя.](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a><span data-ttu-id="73a91-174">□ Шаг 6: включить определенные параметры для каналов</span><span class="sxs-lookup"><span data-stu-id="73a91-174">□ Step 6: Enable specific settings for channels</span></span> 

<span data-ttu-id="73a91-175">В приложении группы на уровне отдельных групп настройте разрешения таким образом, гости могут создание, обновление и удаление каналов.</span><span class="sxs-lookup"><span data-stu-id="73a91-175">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="73a91-176">В дополнение к "Администраторы" Этот параметр можно настроить группы владельцев.</span><span class="sxs-lookup"><span data-stu-id="73a91-176">In addition to admins,  team owners can configure this setting.</span></span>

![Снимок экрана показан пример переключатель параметров на канал группы](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="73a91-178">Для получения дополнительных сведений, в том числе видеоинструкции видеть [гостевой доступ в группах Майкрософт](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="73a91-178">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="73a91-179">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="73a91-179">Troubleshooting</span></span>

<span data-ttu-id="73a91-180">При наличии проблем с добавлением гости в группами Майкрософт, в разделе [Руководство по устранению неполадок доступа гостя](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span><span class="sxs-lookup"><span data-stu-id="73a91-180">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


