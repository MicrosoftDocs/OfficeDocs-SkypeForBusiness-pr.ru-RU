---
title: Контрольный список гостевой группы Microsoft Access
author: romanma
ms.author: romanma
manager: serdars
ms.date: 2/15/18
ms.topic: article
ms.service: msteams
ms.reviewer: rramesan
description: Используйте этот контрольный список для настройки доступа гостя в гостевой группы Microsoft Access.
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4a2ad3c2416e64334dddda6c09d3e8eed2be3763
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374252"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="32980-103">Контрольный список групп доступ в качестве гостя</span><span class="sxs-lookup"><span data-stu-id="32980-103">Teams Guest Access checklist</span></span>
==========================================

<span data-ttu-id="32980-104">Используйте этот контрольный список для включения и настройки компонента доступа в группами Майкрософт в соответствии с предпочтениями вашей организации.</span><span class="sxs-lookup"><span data-stu-id="32980-104">Use this checklist to help you enable and configure the Guest Access feature in Microsoft Teams according to the preferences of your organization.</span></span>




## <a name="--enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="32980-105">□ Enable гостевого доступа на уровне клиента</span><span class="sxs-lookup"><span data-stu-id="32980-105">□  Enable guest access at the tenant level</span></span>

<span data-ttu-id="32980-106">Как минимум необходимо включить группами Майкрософт для всех пользователей тип лицензии **гостя**.</span><span class="sxs-lookup"><span data-stu-id="32980-106">At a minimum, you must turn on Microsoft Teams for all users of the license type **Guest**.</span></span> <span data-ttu-id="32980-107">Подробные инструкции в разделе [Включение и отключение гостевой доступ к группами Майкрософт](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="32980-107">For detailed instructions, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>

![Снимок экрана показан пример переключателя параметров группы](media/guest-access-checklist-TeamsSettings1.png)



## <a name="-enable-specific-settings-for-channels"></a><span data-ttu-id="32980-109">□ Включить определенные параметры для каналов</span><span class="sxs-lookup"><span data-stu-id="32980-109">□ Enable specific settings for channels</span></span> 
<span data-ttu-id="32980-110">В приложении группы на уровне отдельных групп настройте разрешения таким образом, гости могут создание, обновление и удаление каналов.</span><span class="sxs-lookup"><span data-stu-id="32980-110">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="32980-111">В дополнение к "Администраторы" Этот параметр можно настроить группы владельцев.</span><span class="sxs-lookup"><span data-stu-id="32980-111">In addition to admins,  team owners can configure this setting.</span></span>

![Снимок экрана показан пример переключить на канал группы параметров](media/guest-access-checklist-TeamsSettings2.png)


<span data-ttu-id="32980-113">Для получения дополнительных сведений, в том числе видеоинструкции видеть [гостевой доступ в группах Майкрософт](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="32980-113">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>



## <a name="--configure-sharing-in-office-365"></a><span data-ttu-id="32980-114">Настройка □ общего доступа в Office 365</span><span class="sxs-lookup"><span data-stu-id="32980-114">□  Configure Sharing in Office 365</span></span> 

<span data-ttu-id="32980-115">□ Убедитесь, что пользователи могут добавлять Гости.</span><span class="sxs-lookup"><span data-stu-id="32980-115">□ Make sure users can add guests.</span></span> <span data-ttu-id="32980-116">Вот как:</span><span class="sxs-lookup"><span data-stu-id="32980-116">Here's how:</span></span>

1. <span data-ttu-id="32980-117">В центре администрирования Office 365 перейдите в раздел **Параметры** > **безопасности и конфиденциальности**.</span><span class="sxs-lookup"><span data-stu-id="32980-117">In the Office 365 admin center, go to **Settings** > **Security & privacy**.</span></span>
<span data-ttu-id="32980-118">![Снимок экрана показан пример параметры служб](media/guest-access-checklist-Office365Admin_Services_addins.png)</span><span class="sxs-lookup"><span data-stu-id="32980-118">![Screenshot shows an example of a Services settings](media/guest-access-checklist-Office365Admin_Services_addins.png)</span></span>
1. <span data-ttu-id="32980-119">В **общий доступ**выберите команду **Изменить**. ![Снимке экрана показан пример кнопка Изменить параметры общего доступа](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)</span><span class="sxs-lookup"><span data-stu-id="32980-119">In **Sharing**, select **Edit**.![Screenshot shows an example of a Sharing Settings edit button](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)</span></span>
2. <span data-ttu-id="32980-120">Значение **Пользователи могут добавлять новые Гости к данной организации** **на**и нажмите кнопку **Сохранить**. ![Снимке экрана показан пример переключателя параметры общего доступа](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)</span><span class="sxs-lookup"><span data-stu-id="32980-120">Set **Let users add new guests to this organization** to **On**, and then click **Save**.![Screenshot shows an example of a Sharing Settings toggle](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)</span></span>
 

 > [!NOTE]
> <span data-ttu-id="32980-121">Этот параметр эквивалентен параметру **можно пригласить участников** в пользовательские параметры > внешние пользователи в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="32980-121">This setting is equivalent to the **Members can invite** setting in  User settings > External users  in Azure AD.</span></span>  




## <a name="-configure-office-365-groups"></a><span data-ttu-id="32980-122">□ Настройки групп Office 365</span><span class="sxs-lookup"><span data-stu-id="32980-122">□ Configure Office 365 Groups</span></span>

<span data-ttu-id="32980-123">В центре администрирования Office 365 перейдите в раздел **Параметры** > **служб & надстройки** > **Группы Office 365**.</span><span class="sxs-lookup"><span data-stu-id="32980-123">In the Office 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>

<span data-ttu-id="32980-124">Убедитесь в том, что **члены группы за пределами содержимого группе организации клиента** — это значение **на**.</span><span class="sxs-lookup"><span data-stu-id="32980-124">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="32980-125">Если этот параметр отключен, Гости не сможет получить доступ к содержимому любой группы.</span><span class="sxs-lookup"><span data-stu-id="32980-125">If this setting is turned off, guests won't be able to access any group content.</span></span>

<span data-ttu-id="32980-126">Убедитесь в том, что **позволить добавлять пользователей за пределами организации, чтобы группы владельцев группы** — это значение **на**.</span><span class="sxs-lookup"><span data-stu-id="32980-126">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="32980-127">Если этот параметр отключен, владельцев группы не сможет для добавления нового Гости.</span><span class="sxs-lookup"><span data-stu-id="32980-127">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="32980-128">Как минимум этот параметр должен быть «на» для поддержки доступа.</span><span class="sxs-lookup"><span data-stu-id="32980-128">At a minimum,  this setting must be "on" to support guest access.</span></span>

<span data-ttu-id="32980-129">Подробные инструкции по настройке этих параметров в разделе Office 365» группы «в [авторизовать гостевой доступ в группах Майкрософт](Teams-dependencies.md) и [разрешенных и запрещенных гостевой доступ к группам Office 365](https://go.microsoft.com/fwlink/?linkid=869658).</span><span class="sxs-lookup"><span data-stu-id="32980-129">For detailed instructions about configuring these settings, see the section "Office 365 Groups" in [Authorize guest access in Microsoft Teams](Teams-dependencies.md) and [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=869658).</span></span>
 


## <a name="-configure-settings-in-azure-ad-business-to-business-b2b"></a><span data-ttu-id="32980-130">Настройка параметров □ в Azure AD бизнес бизнес (B2B)</span><span class="sxs-lookup"><span data-stu-id="32980-130">□ Configure settings in Azure AD business-to-business (B2B)</span></span>
1. <span data-ttu-id="32980-131">Войдите в https://portal.azure.com.</span><span class="sxs-lookup"><span data-stu-id="32980-131">Sign in to https://portal.azure.com.</span></span>
2. <span data-ttu-id="32980-132">В левой области щелкните **Azure Active directory** .</span><span class="sxs-lookup"><span data-stu-id="32980-132">Click **Azure Active directory** in the left pane.</span></span>
3. <span data-ttu-id="32980-133">В разделе **Управление**щелкните **Параметры пользователя**.</span><span class="sxs-lookup"><span data-stu-id="32980-133">Under **Manage**, click **User settings**.</span></span>
4. <span data-ttu-id="32980-134">В разделе **внешние пользователи**щелкните **Управление внешние параметры совместной работы**</span><span class="sxs-lookup"><span data-stu-id="32980-134">Under **External users**, click **Manage External collaboration settings**</span></span>
5. <span data-ttu-id="32980-135">На странице **параметров внешней совместной работы** убедитесь, что **можно пригласить участников** задано значение **Да**. ![Снимке экрана показан пример AAD параметры переключателя.</span><span class="sxs-lookup"><span data-stu-id="32980-135">On the **External collaboration settings** page make sure **Members can invite** is set to **Yes**.![Screenshot shows an example of a AAD Settings toggle.</span></span> ](media/guest-access-checklist-AADSettings1.png)

    

<span data-ttu-id="32980-136">► По крайней мере для поддержки Гости, **можно пригласить участников** должен иметь значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="32980-136">► At a minimum to support guests, **Members can invite** must be set to **Yes**.</span></span>

> > [!NOTE]
> > <span data-ttu-id="32980-137">Если значение **можно пригласить участников** **Нет** и включения гостевого доступа в Office 365 групп и группами Майкрософт, администраторы могут управлять гостевой приглашения в каталоге.</span><span class="sxs-lookup"><span data-stu-id="32980-137">If you set **Members can invite** to **No** and enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="32980-138">После Гости находятся в каталоге, они могут добавляться к группам участниками без административных прав (группа владельцев).</span><span class="sxs-lookup"><span data-stu-id="32980-138">After guests are in the directory, they can be added to Teams by non-admin members (team owners).</span></span>


<span data-ttu-id="32980-139">Дополнительные сведения см. в статье [Авторизация гостевого доступа в Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="32980-139">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>







## <a name="-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="32980-140">Параметр общего доступа Verify □ в SharePoint</span><span class="sxs-lookup"><span data-stu-id="32980-140">□ Verify sharing setting in SharePoint</span></span>
1. <span data-ttu-id="32980-141">Войдите в Центр администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="32980-141">Sign in to the Office 365 admin center.</span></span>
2. <span data-ttu-id="32980-142">Щелкните **Центр администрирования**, а затем выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="32980-142">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="32980-143">В центре администрирования SharePoint выберите параметр **общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="32980-143">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="32980-144">Убедитесь, что параметр для **не разрешать общий доступ к за пределами организации** *не* установлен. ![Снимке экрана показан пример переключателя Sparepoint параметры в сети.</span><span class="sxs-lookup"><span data-stu-id="32980-144">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.![Screenshot shows an example of a Sparepoint Online Settings toggle.</span></span> ](media/guest-access-checklist-SPOSettings1.png)



## <a name="-verify-account-licenses-and-types"></a><span data-ttu-id="32980-145">□ Проверка учетной записи лицензий и типов</span><span class="sxs-lookup"><span data-stu-id="32980-145">□ Verify account licenses and types</span></span>

- <span data-ttu-id="32980-146">**Учетная запись с корпоративным лицензированием для групп**: для учетной записи «Гость», в реальной учетной записи в некоторые другие клиента Office 365, эта учетная запись реального пользователя должен иметь лицензию для групп на «Гость».</span><span class="sxs-lookup"><span data-stu-id="32980-146">**Account licensed for Teams**: For a "Guest" account rooted in a real user account in some other Office 365 tenant, that real user account must be licensed for Teams for “Guest”.</span></span> 
- <span data-ttu-id="32980-147">**Учетная запись должна будут школа Office 365 или MSA учетную запись, или**: в настоящее время пользователи с адресом электронной почты, соответствующий Azure Active Directory, работы Office 365 или школа учетную запись или учетную запись Майкрософт (MSA) можно добавить как пользователь Гость.</span><span class="sxs-lookup"><span data-stu-id="32980-147">**Account must be Office 365 school or work account, or MSA account**: Currently, users who have an email address corresponding to an Azure Active Directory, Office 365 work or school account, or a Microsoft account (MSA) can be added as a guest user.</span></span> 
 
## <a name="-configure-environment"></a><span data-ttu-id="32980-148">Настройка среды □</span><span class="sxs-lookup"><span data-stu-id="32980-148">□ Configure environment</span></span>


<span data-ttu-id="32980-149">Гости необходимы для использования многофакторная проверка подлинности (многофакторной проверкой Подлинности), если необходимо для размещения клиента.</span><span class="sxs-lookup"><span data-stu-id="32980-149">Guests are required to use multi-factor authentication (MFA) if the hosting tenant requires it.</span></span>
<span data-ttu-id="32980-150">Для получения дополнительных сведений см [модели идентификации и проверки подлинности в группах Майкрософт](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="32980-150">For more details, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="-understand-limitations-for-guests"></a><span data-ttu-id="32980-151">Тщательно изучите ограничения □ для Гости</span><span class="sxs-lookup"><span data-stu-id="32980-151">□ Understand limitations for guests</span></span>

<span data-ttu-id="32980-152">На взаимодействие с гостем имеет ограничения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="32980-152">The guest experience has limitations by design.</span></span> <span data-ttu-id="32980-153">Убедитесь, что изучить гостевой качества, чтобы не пытайтесь исправление, не является источником проблем.</span><span class="sxs-lookup"><span data-stu-id="32980-153">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span>
<span data-ttu-id="32980-154">Далее представлен список некоторых функциональных возможностей, которые недоступен Гость группами Майкрософт, например:</span><span class="sxs-lookup"><span data-stu-id="32980-154">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="32980-155">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="32980-155">OneDrive for Business</span></span>
- <span data-ttu-id="32980-156">Поиск людей не из группы</span><span class="sxs-lookup"><span data-stu-id="32980-156">People search outside of Teams</span></span>
- <span data-ttu-id="32980-157">Календарь, запланированные собрания или сведения о собрании</span><span class="sxs-lookup"><span data-stu-id="32980-157">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="32980-158">ТСОП</span><span class="sxs-lookup"><span data-stu-id="32980-158">PSTN</span></span>
- <span data-ttu-id="32980-159">Организационная диаграмма</span><span class="sxs-lookup"><span data-stu-id="32980-159">Organization chart</span></span>
- <span data-ttu-id="32980-160">Создание или изменение группы</span><span class="sxs-lookup"><span data-stu-id="32980-160">Create or revise a team</span></span>
- <span data-ttu-id="32980-161">Поиск группы</span><span class="sxs-lookup"><span data-stu-id="32980-161">Browse for a team</span></span>
- <span data-ttu-id="32980-162">Передача файлов между двумя пользователями чата</span><span class="sxs-lookup"><span data-stu-id="32980-162">Upload files to a person-to-person chat</span></span>

<span data-ttu-id="32980-163">Для получения дополнительных сведений см [возможности взаимодействия гостя](guest-experience.md) и [гостевой доступ в группах Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="32980-163">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>




## <a name="troubleshooting"></a><span data-ttu-id="32980-164">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="32980-164">Troubleshooting</span></span>

<span data-ttu-id="32980-165">При наличии проблем с добавлением гости в группами Майкрософт, в разделе [Руководство по устранению неполадок доступа гостя](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span><span class="sxs-lookup"><span data-stu-id="32980-165">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


