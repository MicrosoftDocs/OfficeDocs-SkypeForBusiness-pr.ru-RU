---
title: Установка, управление и назначение разрешений для приложения Teams Learning (частная предварительная версия)
author: ChuckEdmonson
ms.author: chucked
manager: pamgreenMSFT
ms.date: ''
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ChrisArnoldMSFT, LearningDocs2020
localization_priority: Normal
search.appverid: ''
ms.collection: ''
description: Используйте приложение Microsoft Teams Learning для создания центрального центра обучения, где сотрудники могут делиться, назначать и изучать материалы из библиотек контента в организации.
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a8fe0d3b4f86de34accb1519c80a391a9e395fbe
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703460"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a><span data-ttu-id="aafd8-103">Установка, управление и назначение разрешений для приложения Teams Learning (частная предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="aafd8-103">Install, manage, and assign permissions for the Teams Learning app (private preview)</span></span>

<span data-ttu-id="aafd8-104">*В этой статье представлены предварительные сведения о приложении Teams Learning в режиме личной предварительной версии.*</span><span class="sxs-lookup"><span data-stu-id="aafd8-104">*This article contains preliminary content for the Teams Learning app, which is in private preview.*</span></span>

<span data-ttu-id="aafd8-105">Приложение Microsoft Teams Learning (частная предварительная версия) позволяет группам и отдельным людям в организации сделать обучение естественным в их дни.</span><span class="sxs-lookup"><span data-stu-id="aafd8-105">The Microsoft Teams Learning app (private preview) empowers teams and individuals in your organization to make learning a natural part of their day.</span></span> <span data-ttu-id="aafd8-106">Приложение создает центр в Teams, где сотрудники могут делиться, назначать и изучать материалы из библиотек содержимого в организации.</span><span class="sxs-lookup"><span data-stu-id="aafd8-106">The app creates a central hub in Teams where employees can share, assign, and learn from content libraries across your organization.</span></span> <span data-ttu-id="aafd8-107">Администраторы устанавливают разрешения и разрешая источники содержимого для обучения приложению.</span><span class="sxs-lookup"><span data-stu-id="aafd8-107">Admins set permissions and allow learning content sources for the app.</span></span> <span data-ttu-id="aafd8-108">Учебный контент может включать в себя учебные материалы LinkedIn Learning, Microsoft Learn, обучение по Microsoft 365, контент вашей организации, хранящаяся в SharePoint Online, и сторонние поставщики, поддерживаемые приложением.</span><span class="sxs-lookup"><span data-stu-id="aafd8-108">Learning content can include LinkedIn Learning, Microsoft Learn, Microsoft 365 training, your organization's own content stored in SharePoint online, and third-party providers that are supported by the app.</span></span>

<span data-ttu-id="aafd8-109">Чтобы настроить приложение Teams Learning (личную предварительную версию), необходимо включить:</span><span class="sxs-lookup"><span data-stu-id="aafd8-109">To set up the Teams Learning app (private preview), you'll need to involve:</span></span>

-   <span data-ttu-id="aafd8-110">Администратор Центра администрирования Teams</span><span class="sxs-lookup"><span data-stu-id="aafd8-110">Teams admin center admin</span></span>
-   <span data-ttu-id="aafd8-111">Администратор Центра администрирования Microsoft 365 (глобальный администратор)</span><span class="sxs-lookup"><span data-stu-id="aafd8-111">Microsoft 365 admin center admin (that is, a global admin)</span></span>
-   <span data-ttu-id="aafd8-112">Администратор знаний (новая роль в Центре администрирования Microsoft 365, которую глобальный администратор (или администратор Microsoft 365) может назначить любому администратору в организации.</span><span class="sxs-lookup"><span data-stu-id="aafd8-112">Knowledge admin (a new role in the Microsoft 365 admin center that a global admin (also known as IT admin or Microsoft 365 admin) can assign to anyone in the organization.</span></span> <span data-ttu-id="aafd8-113">Эта роль управляет источниками контента для обучения организации через Центр администрирования Microsoft 365.)</span><span class="sxs-lookup"><span data-stu-id="aafd8-113">This role manages the organization’s learning content sources through the Microsoft 365 admin center.)</span></span> 

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a><span data-ttu-id="aafd8-114">Управление приложением "Обучение Teams" (частная предварительная версия) в Центре администрирования Teams</span><span class="sxs-lookup"><span data-stu-id="aafd8-114">Manage the Teams Learning app (private preview) in the Teams admin center</span></span>

<span data-ttu-id="aafd8-115">Администратор Teams устанавливает приложение Teams Learning (личную предварительную версию) из магазина приложений и применяет политики настройки, управления и разрешений через Центр администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="aafd8-115">The Teams admin installs the Teams Learning app (private preview) from the app store and applies app setup, manage, and permissions policies through the Teams admin center.</span></span>

### <a name="manage-the-teams-learning-app-private-preview"></a><span data-ttu-id="aafd8-116">Управление приложением Для обучения Teams (частная предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="aafd8-116">Manage the Teams Learning app (private preview)</span></span>

<span data-ttu-id="aafd8-117">Для управления настройками приложения выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="aafd8-117">To manage settings for app, follow these steps:</span></span>

1. <span data-ttu-id="aafd8-118">В левой области навигации Центра администрирования Microsoft Teams перейдите в приложение **Teams**  >  **"Управление приложениями".**</span><span class="sxs-lookup"><span data-stu-id="aafd8-118">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Навигация слева в Центре администрирования Teams с разделами "Приложения Teams" и "Управление приложениями"](media/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="aafd8-120">На странице **"Управление приложениями"** в поле поиска введите *"Обучение",* чтобы найти приложение Teams Learning (предварительная версия).</span><span class="sxs-lookup"><span data-stu-id="aafd8-120">On the **Manage apps** page, in the search box, type *learning* to search for the Teams Learning app (private preview).</span></span>

   ![Страница "Управление приложениями" в Центре администрирования Teams с полем поиска](media/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="aafd8-122">На странице **обучения:**</span><span class="sxs-lookup"><span data-stu-id="aafd8-122">On the **Learning** page:</span></span>
   1. <span data-ttu-id="aafd8-123">В **области "Состояние"** **выберите "Разрешено",** чтобы включить приложение.</span><span class="sxs-lookup"><span data-stu-id="aafd8-123">Under **Status**, select **Allowed** to turn on the app.</span></span>
   2. <span data-ttu-id="aafd8-124">На **вкладке "Параметры"** в разделе "Параметры приложения" перейдите в Центр администрирования Microsoft 365, чтобы настроить источники учебных материалов. </span><span class="sxs-lookup"><span data-stu-id="aafd8-124">On the **Settings** tab, in the **App settings** section, go to the Microsoft 365 admin center to configure learning content sources.</span></span>

   ![Страница обучения в Центре администрирования Teams с разделом "Состояние и параметры приложений"](media/learning-app-teams-learning-page.png)

4. <span data-ttu-id="aafd8-126">После **настройки** параметров приложения  перейдите к настройкам "Разрешения" и "Политики настройки", чтобы предоставить сотрудникам доступ к приложению в рамках участия вашей организации в закрытой предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="aafd8-126">After **Manage app** settings, go to **Permissions and Set-up policies** to grant permission to employees who should have access to the app as part of your organization's participation in the private preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="aafd8-127">Если ваша организация входит в круг 4.0 в рамках программы Teams TAP100, вам может потребоваться сделать следующее, чтобы включить утвержденных пользователей в Ring 3.0 для доступа к приложению Teams Learning (частная предварительная версия).</span><span class="sxs-lookup"><span data-stu-id="aafd8-127">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to do the following to enable approved users in Ring 3.0 to access the Teams Learning app (private preview).</span></span>

<span data-ttu-id="aafd8-128">В рамках личной предварительной версии приложение Teams Learning (частная предварительная версия) выпущено в ring 3.0.</span><span class="sxs-lookup"><span data-stu-id="aafd8-128">As part of private preview, the Teams Learning app (private preview) is released in Ring 3.0.</span></span> <span data-ttu-id="aafd8-129">Если ваша организация находится в ring 4.0, вы не увидите приложение в магазине приложений.</span><span class="sxs-lookup"><span data-stu-id="aafd8-129">If your organization is in Ring 4.0, you won’t see the app in the app store.</span></span> <span data-ttu-id="aafd8-130">Чтобы проверить приложение, необходимо создать настраиваемую политику разрешений для приложений, установить в ней разрешение для всех приложений и назначить ее пользователям, утвержденным в Ring 3.0. </span><span class="sxs-lookup"><span data-stu-id="aafd8-130">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span>

   ![Страница TAP-AppsPermission-Plcy, на которой выбрана кнопка "Разрешить все приложения"](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a><span data-ttu-id="aafd8-132">Настройка источников обучающего контента в Центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aafd8-132">Configure learning content sources in the Microsoft 365 admin center</span></span>

<span data-ttu-id="aafd8-133">Администраторы Центра администрирования Microsoft 365 (самостоятельно или путем назначения роли администратора знаний выбранным лицам в организации) могут управлять настройками, связанными с приложением Teams Learning (личной предварительной версией), и настраивать источники содержимого для обучения.</span><span class="sxs-lookup"><span data-stu-id="aafd8-133">The admins for the Microsoft 365 admin center—either by themselves or by assigning the Knowledge admin role to selected individuals in your organization—can manage settings related to the Teams Learning app (private preview) and can configure the learning content sources.</span></span>

> [!TIP]
> <span data-ttu-id="aafd8-134">Администратору знаний следует быть техническими и иметь существующие учетные данные администратора SharePoint, желательно, чтобы тот, кто хорошо разбирался в образовании, обучении, обучении или опыте работы сотрудников в организации.</span><span class="sxs-lookup"><span data-stu-id="aafd8-134">The Knowledge admin should be moderately technical and have existing SharePoint admin credentials, preferably someone who is well-versed in the education, learning, training, or employee experience part of the organization.</span></span>
 
<span data-ttu-id="aafd8-135">Администратор выбирает, какие из источников обучающего контента (например, LinkedIn Learning или SharePoint) будут доступны в приложении.</span><span class="sxs-lookup"><span data-stu-id="aafd8-135">The admin selects which learning content sources (such as LinkedIn Learning or SharePoint) will be available in the app.</span></span> <span data-ttu-id="aafd8-136">Затем администратор настраивает эти источники, чтобы контент был доступен для поиска и обнаружения и был доступен сотрудникам, работающим с приложением.</span><span class="sxs-lookup"><span data-stu-id="aafd8-136">The admin then configures those sources to make sure the content is available for search and discovery and can be browsed by the employees who use the app.</span></span>

### <a name="assign-the-knowledge-admin-role-optional"></a><span data-ttu-id="aafd8-137">Назначение роли администратора знаний [Необязательно]</span><span class="sxs-lookup"><span data-stu-id="aafd8-137">Assign the Knowledge admin role [Optional]</span></span>

<span data-ttu-id="aafd8-138">Эти действия должен выполнить администратор Центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aafd8-138">These steps are to be performed by the admin for the Microsoft 365 admin center.</span></span>

1.  <span data-ttu-id="aafd8-139">В левой области навигации Центра администрирования Microsoft 365 перейдите к области **"Роли".**</span><span class="sxs-lookup"><span data-stu-id="aafd8-139">In the left navigation of the Microsoft 365 admin center, go to **Roles**.</span></span>

2.  <span data-ttu-id="aafd8-140">На странице **"Роли"** на вкладке **Azure AD** выберите **"Администратор знаний".**</span><span class="sxs-lookup"><span data-stu-id="aafd8-140">On the **Roles** page, on the **Azure AD** tab, select **Knowledge admin**.</span></span>
 
3.  <span data-ttu-id="aafd8-141">На странице **"Администратор знаний"** в разделе **"Назначенные** администраторы" выберите "Добавить", а затем добавьте нужного человека.</span><span class="sxs-lookup"><span data-stu-id="aafd8-141">On the **Knowledge admin** page, in the **Assigned Admins** section, select **Add**, and then add the person you choose for the role.</span></span>

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a><span data-ttu-id="aafd8-142">Настройка параметров для источников обучающего контента для приложения</span><span class="sxs-lookup"><span data-stu-id="aafd8-142">Configure settings for the learning content sources for the app</span></span>

<span data-ttu-id="aafd8-143">Эти действия должны выполняться администратором Microsoft 365 или администратором знаний.</span><span class="sxs-lookup"><span data-stu-id="aafd8-143">These steps are to be performed by the Microsoft 365 admin or the Knowledge admin.</span></span>

1.  <span data-ttu-id="aafd8-144">В левой области навигации Центра администрирования Microsoft 365 перейдите в настройки  >  организации.</span><span class="sxs-lookup"><span data-stu-id="aafd8-144">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>

2.  <span data-ttu-id="aafd8-145">На странице **"Параметры"** на вкладке "& **Службы"** выберите приложение **"Обучение".**</span><span class="sxs-lookup"><span data-stu-id="aafd8-145">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![Страница параметров в Центре администрирования Microsoft 365 с перечисленным приложением "Обучение"](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="aafd8-147">На панели **приложения "Обучение"** выберите источники учебных материалов, которые вы хотите настроить для организации, и выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="aafd8-147">On the **Learning app** panel, select the learning content sources you want to configure for the organization, and then select **Save**.</span></span>

   ![Панель приложения "Обучение" в Центре администрирования Microsoft 365 с вариантами источников контента](media/learning-app-365-settings-learning-app-panel.png)

<span data-ttu-id="aafd8-149">Некоторые из источников обучения будут включены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="aafd8-149">Among all the learning sources that exist, some will be enabled by default.</span></span> <span data-ttu-id="aafd8-150">В их числе:</span><span class="sxs-lookup"><span data-stu-id="aafd8-150">These include:</span></span>

- <span data-ttu-id="aafd8-151">LinkedIn Learning (бесплатное содержимое)</span><span class="sxs-lookup"><span data-stu-id="aafd8-151">LinkedIn Learning (free content)</span></span>
- <span data-ttu-id="aafd8-152">Microsoft Learn</span><span class="sxs-lookup"><span data-stu-id="aafd8-152">Microsoft Learn</span></span>
- <span data-ttu-id="aafd8-153">Обучение по Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aafd8-153">Microsoft 365 Training</span></span>

> [!NOTE]
> <span data-ttu-id="aafd8-154">Если у вашей организации есть подписка на LinkedIn Learning Стандартный или Pro, репозиторий контента будет разблокирован для сотрудников организации.</span><span class="sxs-lookup"><span data-stu-id="aafd8-154">If your organization has a LinkedIn Learning Standard or Pro subscription, the content repository will be unlocked for the employees in your organization.</span></span> <span data-ttu-id="aafd8-155">Использовать весь репозиторий контента смогут только те сотрудники, у которых есть разрешение.</span><span class="sxs-lookup"><span data-stu-id="aafd8-155">Only those employees who have permission will be able to use the entire content repository.</span></span>

<span data-ttu-id="aafd8-156">Другие источники может потребоваться включить или настроить вручную.</span><span class="sxs-lookup"><span data-stu-id="aafd8-156">Other sources might need to be enabled or configured manually.</span></span> <span data-ttu-id="aafd8-157">Источники обучения, не от корпорации Майкрософт, лицензируются отдельно между вашей организацией и третьими сторонами.</span><span class="sxs-lookup"><span data-stu-id="aafd8-157">Learning sources that are not from Microsoft are separately licensed between your organization and the third party.</span></span> <span data-ttu-id="aafd8-158">Вам потребуется подтвердить, что вы подписались на обучение для вас и ваших пользователей.</span><span class="sxs-lookup"><span data-stu-id="aafd8-158">You’ll need to verify you’ve signed up for their learning for you and your users.</span></span>

<span data-ttu-id="aafd8-159">Чтобы включить или отключить источник обучающего контента, выберите его, чтобы включить или отключить его.</span><span class="sxs-lookup"><span data-stu-id="aafd8-159">To enable or disable a learning content source, select the check box next to the source.</span></span> <span data-ttu-id="aafd8-160">Если источник включен, будет виден контрольный знак.</span><span class="sxs-lookup"><span data-stu-id="aafd8-160">If a source is enabled, a check mark will be visible.</span></span>

## <a name="configure-sharepoint-as-a-learning-content-source"></a><span data-ttu-id="aafd8-161">Настройка SharePoint в качестве источника содержимого для обучения</span><span class="sxs-lookup"><span data-stu-id="aafd8-161">Configure SharePoint as a learning content source</span></span>

<span data-ttu-id="aafd8-162">Вы можете настроить SharePoint в качестве источника содержимого для обучения в приложении Teams Learning (при личной предварительной версии) в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aafd8-162">You configure SharePoint as a learning content source for the Teams Learning app (private preview) in the Microsoft 365 admin center.</span></span>

### <a name="overview"></a><span data-ttu-id="aafd8-163">Обзор</span><span class="sxs-lookup"><span data-stu-id="aafd8-163">Overview</span></span>

<span data-ttu-id="aafd8-164">Администратор знаний предоставляет URL-адрес сайта, на котором служба обучения может создать пустой централизованный репозиторий контента для обучения в виде структурированного списка SharePoint.</span><span class="sxs-lookup"><span data-stu-id="aafd8-164">The Knowledge admin provides a site URL to where the Learning Service can create an empty centralized learning content repository in the form of a structured SharePoint list.</span></span> <span data-ttu-id="aafd8-165">Организация может использовать этот список для организации для организации ссылок на папки SharePoint разных компаний, содержащие учебный контент.</span><span class="sxs-lookup"><span data-stu-id="aafd8-165">This list can be used by the organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="aafd8-166">Администраторы отвечают за сбор и просмотр списка URL-адресов папок.</span><span class="sxs-lookup"><span data-stu-id="aafd8-166">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="aafd8-167">Эти папки должны включать только содержимое, которое можно сделать доступным в приложении Teams Learning (частная предварительная версия).</span><span class="sxs-lookup"><span data-stu-id="aafd8-167">These folders should only include content that can be made available in the Teams Learning app (private preview).</span></span>

### <a name="permissions"></a><span data-ttu-id="aafd8-168">Разрешения</span><span class="sxs-lookup"><span data-stu-id="aafd8-168">Permissions</span></span>

<span data-ttu-id="aafd8-169">URL-адреса папок можно собрать на любом сайте SharePoint в организации.</span><span class="sxs-lookup"><span data-stu-id="aafd8-169">Folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="aafd8-170">Поиск будет использоваться в любом содержимом в этих папках, но будет использоваться только тот контент, к которому у конкретного сотрудника есть разрешения.</span><span class="sxs-lookup"><span data-stu-id="aafd8-170">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>
 
### <a name="learning-service"></a><span data-ttu-id="aafd8-171">Служба обучения</span><span class="sxs-lookup"><span data-stu-id="aafd8-171">Learning Service</span></span>

<span data-ttu-id="aafd8-172">Служба обучения использует предоставленные URL-адреса папок для получения метаданных из всего содержимого, храняного в этих папках.</span><span class="sxs-lookup"><span data-stu-id="aafd8-172">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="aafd8-173">В течение 24 часов после того, как url-адрес папки будет указан в централизованном репозитории, сотрудники смогут искать и использовать содержимое компании в приложении.</span><span class="sxs-lookup"><span data-stu-id="aafd8-173">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use the company’s content within the app.</span></span> <span data-ttu-id="aafd8-174">Удаление контента из репозитория на этом этапе не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="aafd8-174">Content deletion from the repository isn't supported at this point.</span></span> <span data-ttu-id="aafd8-175">Непреднамеренно выставляемый контент можно удалить только путем ссылки нового URL-адреса сайта SharePoint в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aafd8-175">Unintentionally surfaced content can only be removed by supplying a new SharePoint site URL in the Microsoft 365 admin center.</span></span>

### <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="aafd8-176">Настройка SharePoint в качестве источника</span><span class="sxs-lookup"><span data-stu-id="aafd8-176">Configure SharePoint as a source</span></span>

<span data-ttu-id="aafd8-177">Эти действия должны выполняться администратором Microsoft 365 или администратором знаний.</span><span class="sxs-lookup"><span data-stu-id="aafd8-177">These steps are to be performed by Microsoft 365 admin or the Knowledge admin.</span></span>

1.  <span data-ttu-id="aafd8-178">В левой области навигации Центра администрирования Microsoft 365 перейдите в меню **"Параметры".**</span><span class="sxs-lookup"><span data-stu-id="aafd8-178">In the left navigation of the Microsoft 365 admin center, go to **Settings**.</span></span>
 
2.  <span data-ttu-id="aafd8-179">На странице **"Параметры"** на вкладке "& **Службы"** выберите приложение **"Обучение".**</span><span class="sxs-lookup"><span data-stu-id="aafd8-179">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![Страница параметров в Центре администрирования Microsoft 365 с перечисленным приложением "Обучение"](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="aafd8-181">На панели **приложения "Обучение"** в url-адрес сайта SharePoint, где вы хотите создать централизованный репозиторий.</span><span class="sxs-lookup"><span data-stu-id="aafd8-181">On the **Learning app** panel, provide the site URL to the SharePoint site where you want the app to create a centralized repository.</span></span>

   ![Панель приложения "Обучение" в Центре администрирования Microsoft 365 с выбранным приложением SharePoint](media/learning-app-365-panel-sharepoint-selected.png)

4.  <span data-ttu-id="aafd8-183">Список SharePoint создается автоматически на сайте SharePoint предоставленной организации.</span><span class="sxs-lookup"><span data-stu-id="aafd8-183">A SharePoint list is created automatically within the provided organization’s SharePoint site.</span></span> <span data-ttu-id="aafd8-184">В левой области навигации сайта SharePoint выберите репозиторий контента **для обучения.**</span><span class="sxs-lookup"><span data-stu-id="aafd8-184">In the left navigation of the SharePoint site, select **Learning App Content Repository**.</span></span> 

   ![Левая навигация в SharePoint с разделом "Репозиторий контента для приложений для обучения"](media/learning-app-content-repository-nav.png)

 
5. <span data-ttu-id="aafd8-186">На странице **"Репозиторий контента** для обучения" заполнять список SharePoint URL-адресами папок обучающего контента.</span><span class="sxs-lookup"><span data-stu-id="aafd8-186">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1.   <span data-ttu-id="aafd8-187">Выберите **"Новое",** чтобы **просмотреть панель "Новый элемент".**</span><span class="sxs-lookup"><span data-stu-id="aafd8-187">Select **New** to view the **New item** panel.</span></span> 

   ![Страница "Репозиторий контента для обучения" в SharePoint с параметром "Новый"](media/learning-app-content-repository-new.png)
 
   2.   <span data-ttu-id="aafd8-189">На панели **"Новый элемент"** в поле **"Название"** добавьте название каталога по вашему выбору.</span><span class="sxs-lookup"><span data-stu-id="aafd8-189">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="aafd8-190">В поле **"URL-адрес папки"** добавьте URL-адрес в папку содержимого для обучения.</span><span class="sxs-lookup"><span data-stu-id="aafd8-190">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="aafd8-191">Выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="aafd8-191">Select **Save**.</span></span>

   ![Панель "Новый элемент" в SharePoint с полями "Название" и "URL-адрес папки"](media/learning-app-new-item-panel.png)

   3. <span data-ttu-id="aafd8-193">На странице "Репозиторий контента для учебных приложений" будет обновлено новое содержимое для обучения.</span><span class="sxs-lookup"><span data-stu-id="aafd8-193">The Learning App Content Repository page is updated with the new learning content.</span></span>

   ![Страница "Репозиторий контента приложений для обучения" в SharePoint с обновленными сведениями](media/learning-app-content-repository-populated.png)


 


