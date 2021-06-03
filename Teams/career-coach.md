---
title: Приобрести, настроить и включить для тренеров по Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Узнайте, как приобрести, настроить и включить тренера по Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a16f6cbb3d6ade57a81bb245c42c5ea0917f849
ms.sourcegitcommit: 19b9904588fcc14398e65b4153ab9fe7f5dd6a5d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2021
ms.locfileid: "52729807"
---
# <a name="purchase-configure-and-enable-career-coach-for-microsoft-teams"></a><span data-ttu-id="ec7d6-103">Приобрести, настроить и включить для тренеров по Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ec7d6-103">Purchase, configure, and enable Career Coach for Microsoft Teams</span></span>

<span data-ttu-id="ec7d6-104">Career Coach — это приложение Microsoft Teams для образовательных сфере, которое работает на сайте LinkedIn и предоставляет учащимся более высокого уровня индивидуальные рекомендации по переходу к карьере.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-104">Career Coach is a Microsoft Teams for Education app powered by LinkedIn that provides personalized guidance for higher education students to navigate their career journey.</span></span> <span data-ttu-id="ec7d6-105">Тренер по карьерной подготовке предлагает учебным заведениям единое решение для карьерных целей, которое позволяет учащимся найти свой путь к карьере, развивать реальные навыки и создать свою сеть в одном месте.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-105">Career Coach offers educational institutions a unified career solution for students to discover their career path, grow real-world skills, and build their network all in one place.</span></span>

<span data-ttu-id="ec7d6-106">Подробнее о [тренере по карьерной карьере.](https://aka.ms/career-coach)</span><span class="sxs-lookup"><span data-stu-id="ec7d6-106">Learn more about [Career Coach](https://aka.ms/career-coach).</span></span>

> [!NOTE]
> <span data-ttu-id="ec7d6-107">Используйте рекомендации и полезные советы из этого руководства, чтобы включить возможности тренера по карьерной деятельности для студентов, преподавателей и сотрудников.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-107">Use the best practices and helpful tips in this guide to enable the capabilities of Career Coach for students, faculty, and staff.</span></span> <span data-ttu-id="ec7d6-108">См. [статью Краткое руководство по планированию.](https://support.microsoft.com/office/c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4)</span><span class="sxs-lookup"><span data-stu-id="ec7d6-108">See the [Quick planning guide](https://support.microsoft.com/office/c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4) article.</span></span>

## <a name="review-the-requirements"></a><span data-ttu-id="ec7d6-109">Проверка требований</span><span class="sxs-lookup"><span data-stu-id="ec7d6-109">Review the requirements</span></span>

<span data-ttu-id="ec7d6-110">Чтобы включить для вашего учебного заведения функцию "Тренер по карьерной работе", просмотрите, что нужно для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-110">To enable Career Coach for your educational institution, review what you need to get the app up and running.</span></span>

<span data-ttu-id="ec7d6-111">**Технические требования**</span><span class="sxs-lookup"><span data-stu-id="ec7d6-111">**Technical requirements**</span></span>

  - <span data-ttu-id="ec7d6-112">Office 365 с Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ec7d6-112">Office 365 tenant with Azure Active Directory</span></span>

  - <span data-ttu-id="ec7d6-113">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ec7d6-113">Microsoft Teams</span></span>

  - <span data-ttu-id="ec7d6-114">Подключения учетной записи LinkedIn в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ec7d6-114">LinkedIn account connections in Azure Active Directory</span></span>

<span data-ttu-id="ec7d6-115">**Лицензии**</span><span class="sxs-lookup"><span data-stu-id="ec7d6-115">**Licenses**</span></span>

  - <span data-ttu-id="ec7d6-116">Факультет</span><span class="sxs-lookup"><span data-stu-id="ec7d6-116">Faculty</span></span> 

  - <span data-ttu-id="ec7d6-117">Студентов</span><span class="sxs-lookup"><span data-stu-id="ec7d6-117">Students</span></span>

> [!NOTE]
> <span data-ttu-id="ec7d6-118">ИТ-администратору, заполняющий конфигурацию, должна быть назначена лицензия преподавателя по карьерной деятельности.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-118">A Career Coach Faculty license must be assigned to the IT admin completing the configuration.</span></span>

<span data-ttu-id="ec7d6-119">**Данные и файлы из вашего учебного заведения**</span><span class="sxs-lookup"><span data-stu-id="ec7d6-119">**Data and files from your educational institution**</span></span>

  - <span data-ttu-id="ec7d6-120">Данные каталога курса</span><span class="sxs-lookup"><span data-stu-id="ec7d6-120">Course catalog data</span></span>

  - <span data-ttu-id="ec7d6-121">Предлагаемые поля исследования</span><span class="sxs-lookup"><span data-stu-id="ec7d6-121">Fields of study offered</span></span>

  - <span data-ttu-id="ec7d6-122">Страница LinkedIn образовательного учреждения</span><span class="sxs-lookup"><span data-stu-id="ec7d6-122">Educational institution’s LinkedIn page</span></span>

  - <span data-ttu-id="ec7d6-123">Подписка на LinkedIn Learning campus (предпочитаемая)</span><span class="sxs-lookup"><span data-stu-id="ec7d6-123">LinkedIn Learning campus subscription (preferred)</span></span>

## <a name="purchase-the-career-coach-licenses"></a><span data-ttu-id="ec7d6-124">Приобретение лицензий для тренера по карьерной карьере</span><span class="sxs-lookup"><span data-stu-id="ec7d6-124">Purchase the Career Coach licenses</span></span>

<span data-ttu-id="ec7d6-125">Она доступна по всему миру (за исключением Китая и России) для квалифицированных высших учебных заведений с помощью регистрации решений для образовательных учреждений (EES), поставщиков облачных услуг (CSP) и Microsoft 365 администрирования (прямой веб-сайт).</span><span class="sxs-lookup"><span data-stu-id="ec7d6-125">Career Coach is available worldwide (except China and Russia) for qualified higher education institutions through Enrollment for Education Solutions (EES), Cloud Service Providers (CSP), and Microsoft 365 admin center (web direct).</span></span> <span data-ttu-id="ec7d6-126">Как приложение Microsoft Teams, клиенты должны Microsoft 365 A3/A5 или Office 365 A1/A3/A5.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-126">As a Microsoft Teams app, customers must have Microsoft 365 A3/A5 or Office 365 A1/A3/A5.</span></span>

### <a name="assign-app-licenses-to-users"></a><span data-ttu-id="ec7d6-127">Назначение лицензий на приложения пользователям</span><span class="sxs-lookup"><span data-stu-id="ec7d6-127">Assign app licenses to users</span></span>

<span data-ttu-id="ec7d6-128">Пошаговую инструкцию см. в инструкциях по [назначению лицензий пользователям.](/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="ec7d6-128">For step-by-step instructions, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="turn-on-linkedin-account-connections"></a><span data-ttu-id="ec7d6-129">Включить подключения к учетной записи LinkedIn</span><span class="sxs-lookup"><span data-stu-id="ec7d6-129">Turn on LinkedIn account connections</span></span>

<span data-ttu-id="ec7d6-130">Чтобы **упростить** работу тренера по карьерной карьере, пользователи учебного заведения должны иметь возможность подключить свою учетную запись Microsoft 365 к учетной записи LinkedIn, которая упростилась в рамках тренера по карьерной карьере.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-130">Career Coach **requires** your educational institution’s users to have the ability to connect their Microsoft 365 account to their LinkedIn account that is facilitated within Career Coach</span></span>

1. <span data-ttu-id="ec7d6-131">Во sign in the [Azure AD admin center](https://aad.portal.azure.com/) with an account that's a global admin for the Azure AD organization.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-131">Sign in to the [Azure AD admin center](https://aad.portal.azure.com/) with an account that's a global admin for the Azure AD organization.</span></span>

2. <span data-ttu-id="ec7d6-132">Выберите **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-132">Select **Users**.</span></span>

3. <span data-ttu-id="ec7d6-133">На странице **Пользователи** выберите **Параметры пользователя**.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-133">On the **Users** page, select **User settings**.</span></span>

4. <span data-ttu-id="ec7d6-134">В **области Подключения к учетной записи LinkedIn** разрешить пользователям подключать свои учетные записи для доступа к своим подключениям LinkedIn в некоторых приложениях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-134">Under **LinkedIn account connections**, allow users to connect their accounts to access their LinkedIn connections within some Microsoft apps.</span></span> <span data-ttu-id="ec7d6-135">Никакие данные не делиться, пока пользователи не согласится подключить свои учетные записи.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-135">No data is shared until users consent to connect their accounts.</span></span>

   - <span data-ttu-id="ec7d6-136">Выберите **Да,** чтобы включить службу для всех пользователей в образовательном учреждении</span><span class="sxs-lookup"><span data-stu-id="ec7d6-136">Select **Yes** to enable the service for all users in your educational institution</span></span>

   - <span data-ttu-id="ec7d6-137">Выберите **выбранную группу,** чтобы включить службу только для группы выбранных пользователей в вашем образовательном учреждении</span><span class="sxs-lookup"><span data-stu-id="ec7d6-137">Select **Selected group** to enable the service for only a group of selected users in your educational institution</span></span>

   - <span data-ttu-id="ec7d6-138">Выберите **Нет,** чтобы отозвать согласие всех пользователей в образовательном учреждении</span><span class="sxs-lookup"><span data-stu-id="ec7d6-138">Select **No** to withdraw consent from all users in your educational institution</span></span>

<span data-ttu-id="ec7d6-139">Узнайте, как [интегрировать подключения учетной записи LinkedIn в Azure Active Directory](/azure/active-directory/enterprise-users/linkedin-integration)</span><span class="sxs-lookup"><span data-stu-id="ec7d6-139">Learn how to [Integrate LinkedIn account connections in Azure Active Directory](/azure/active-directory/enterprise-users/linkedin-integration)</span></span>

## <a name="configure-career-coach-in-the-teams-admin-center"></a><span data-ttu-id="ec7d6-140">Настройка тренера по карьерной Teams центре администрирования</span><span class="sxs-lookup"><span data-stu-id="ec7d6-140">Configure Career Coach in the Teams admin center</span></span>

<span data-ttu-id="ec7d6-141">Используя параметры администрирования в Центре Microsoft Teams, вы можете настроить его для своего учебного заведения и включить для пользователей.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-141">Using the admin settings in the Microsoft Teams admin center, you can configure Career Coach for your educational institution and enable it for users.</span></span>

## <a name="access-the-career-coach-app-settings"></a><span data-ttu-id="ec7d6-142">Доступ к настройкам приложения "Тренер по карьерной карьере"</span><span class="sxs-lookup"><span data-stu-id="ec7d6-142">Access the Career Coach app settings</span></span>

<span data-ttu-id="ec7d6-143">На странице [Управление приложениями](/microsoftteams/manage-apps) можно просмотреть Teams приложения в каталоге приложений учебного заведения.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-143">Use the [Manage apps page](/microsoftteams/manage-apps) to view the Teams apps in your educational institution’s app catalog.</span></span>

1. <span data-ttu-id="ec7d6-144">Во sign in to the **Teams admin center**.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-144">Sign in to the **Teams admin center**.</span></span>

2. <span data-ttu-id="ec7d6-145">В левой области навигации выберите Teams **приложения**  >  **Управление приложениями**.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-145">In the left navigation, select **Teams apps** > **Manage apps**.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="ec7d6-146">Для доступа к странице необходимо быть глобальным Teams администратором службы.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-146">You must be a global admin or Teams service admin to access the page.</span></span>

3. <span data-ttu-id="ec7d6-147">Поиск или поиск по **запросу "Тренер по карьерной работе"**.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-147">Search or browse for **Career Coach**.</span></span>  

4. <span data-ttu-id="ec7d6-148">Выберите **Тренер по карьерной** деятельности , а затем выберите **Параметры.**</span><span class="sxs-lookup"><span data-stu-id="ec7d6-148">Select **Career Coach**, and then select **Settings.**</span></span>  

    ![Приложение "Тренер по карьерной карьере", выбранное с параметром Параметры с отображением](media/career-coach-app.png)

### <a name="configure-the-career-coach-app-settings"></a><span data-ttu-id="ec7d6-150">Настройка параметров приложения "Тренер по карьерной карьере"</span><span class="sxs-lookup"><span data-stu-id="ec7d6-150">Configure the Career Coach app settings</span></span>

<span data-ttu-id="ec7d6-151">У тренера по карьерной карьере пять категорий конфигураций:</span><span class="sxs-lookup"><span data-stu-id="ec7d6-151">Career Coach has five configuration categories:</span></span>

- [<span data-ttu-id="ec7d6-152">Торговая марка и параметры</span><span class="sxs-lookup"><span data-stu-id="ec7d6-152">Brand and preferences</span></span>](#brand-and-preferences)

- [<span data-ttu-id="ec7d6-153">Конфигурация LinkedIn</span><span class="sxs-lookup"><span data-stu-id="ec7d6-153">LinkedIn configuration</span></span>](#linkedin-configuration)

- [<span data-ttu-id="ec7d6-154">Каталог курса</span><span class="sxs-lookup"><span data-stu-id="ec7d6-154">Course catalog</span></span>](#course-catalog)

- [<span data-ttu-id="ec7d6-155">Поля исследования</span><span class="sxs-lookup"><span data-stu-id="ec7d6-155">Fields of study</span></span>](#fields-of-study)

- [<span data-ttu-id="ec7d6-156">Настройки</span><span class="sxs-lookup"><span data-stu-id="ec7d6-156">Customization</span></span>](#customization)

> [!NOTE]
> <span data-ttu-id="ec7d6-157">Чтобы эффективно включить приложение для студентов, преподавателей и  сотрудников, необходимо использовать фирменную марку и параметры, конфигурацию LinkedIn, каталог курса и поля обучения.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-157">Brand and preferences, LinkedIn configuration, Course catalog, and Fields of study are **required** to effectively enable the app for students, faculty, and staff.</span></span>

#### <a name="brand-and-preferences"></a><span data-ttu-id="ec7d6-158">Торговая марка и параметры</span><span class="sxs-lookup"><span data-stu-id="ec7d6-158">Brand and preferences</span></span>

<span data-ttu-id="ec7d6-159">Задайте название, логотип и язык по умолчанию учебного заведения на странице параметров и фирме.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-159">Set your educational institution’s name, logo, and default language on the brand and preferences settings page.</span></span>

![Раздел фирменой фирменой маркы "Тренер по карьерной карьере" в Центре администрирования](media/career-coach-brand.png)

##### <a name="educational-institution-icon"></a><span data-ttu-id="ec7d6-161">Значок образовательного учреждения</span><span class="sxs-lookup"><span data-stu-id="ec7d6-161">Educational institution icon</span></span>

<span data-ttu-id="ec7d6-162">Значок учебного заведения используется во всем приложении "Тренер по карьерной деятельности", чтобы идентифицировать содержимое, уникальное для вашего учебного заведения, ресурсы каталога курса во всем приложении и в разделе реальных функций панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-162">The educational institution icon is used throughout Career Coach to identify content unique to your educational institution, course catalog resources throughout the app, and on the real-world experiences section of the dashboard.</span></span> <span data-ttu-id="ec7d6-163">Значок лучше всего отформатирован как:</span><span class="sxs-lookup"><span data-stu-id="ec7d6-163">The icon is best formatted as:</span></span>

 - <span data-ttu-id="ec7d6-164">Прозрачный PNG</span><span class="sxs-lookup"><span data-stu-id="ec7d6-164">A transparent PNG</span></span>
 - <span data-ttu-id="ec7d6-165">Пропорции 1:1</span><span class="sxs-lookup"><span data-stu-id="ec7d6-165">Aspect ratio of 1:1</span></span>
 - <span data-ttu-id="ec7d6-166">Максимальный размер: 64 px x 64 px.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-166">Maximum size of 64 px x 64 px.</span></span>

##### <a name="educational-institution-thumbnail"></a><span data-ttu-id="ec7d6-167">Эскиз образовательного учреждения</span><span class="sxs-lookup"><span data-stu-id="ec7d6-167">Educational institution thumbnail</span></span>

<span data-ttu-id="ec7d6-168">Значок учебного заведения будет использоваться для ресурсов каталога курсов во всем приложении, если определенное изображение не доступно для курса.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-168">The educational institution icon will be used for course catalog resources throughout the app when a specific image isn't available for a course.</span></span> <span data-ttu-id="ec7d6-169">Значок лучше всего отформатирован как:</span><span class="sxs-lookup"><span data-stu-id="ec7d6-169">The icon is best formatted as:</span></span>

- <span data-ttu-id="ec7d6-170">A PNG</span><span class="sxs-lookup"><span data-stu-id="ec7d6-170">A PNG</span></span>
- <span data-ttu-id="ec7d6-171">Пропорции 16:9</span><span class="sxs-lookup"><span data-stu-id="ec7d6-171">Aspect ratio of 16:9</span></span>
- <span data-ttu-id="ec7d6-172">Максимальный размер: 360 px x 200 px.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-172">Maximum size of 360 px x 200 px.</span></span>

#### <a name="linkedin-configuration"></a><span data-ttu-id="ec7d6-173">Конфигурация LinkedIn</span><span class="sxs-lookup"><span data-stu-id="ec7d6-173">LinkedIn configuration</span></span>

<span data-ttu-id="ec7d6-174">Конфигурация LinkedIn связывает Тренера по карьерной деятельности с данными общедоступных выпускников из LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-174">The LinkedIn configuration connects Career Coach with public alumni data from LinkedIn.</span></span>

> [!NOTE]
> <span data-ttu-id="ec7d6-175">Невозможно включить тренера по карьерной карьере без проверки подключения к странице LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-175">Career Coach can't be enabled without the LinkedIn page connection verified.</span></span>

##### <a name="add-and-confirm-the-linkedin-page"></a><span data-ttu-id="ec7d6-176">Добавление и подтверждение страницы LinkedIn</span><span class="sxs-lookup"><span data-stu-id="ec7d6-176">Add and confirm the LinkedIn page</span></span>

<span data-ttu-id="ec7d6-177">Определите страницу LinkedIn учебного заведения.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-177">Determine the educational institution's LinkedIn page.</span></span> <span data-ttu-id="ec7d6-178">Найдите страницу LinkedIn, вы можете найти ее в LinkedIn или связаться с сотрудником, который является сотрудником службы по карьерной карьере, чтобы определить правильную страницу.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-178">Find the LinkedIn page by searching on LinkedIn or connecting with a career services staff member to determine the correct page to use.</span></span>  
  
1. <span data-ttu-id="ec7d6-179">Во sign in to the **Teams admin center**.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-179">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="ec7d6-180">Выберите Teams **приложения Управление**  >  **приложениями Подключение** к  >  **LinkedIn Для**  >  **тренеров по карьерной карьере**.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-180">Select **Teams apps** > **Manage apps** > **Career Coach** > **LinkedIn connection**.</span></span>

2. <span data-ttu-id="ec7d6-181">Введите URL-адрес страницы LinkedIn учебного заведения.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-181">Enter your educational institution's LinkedIn page URL.</span></span>  

3. <span data-ttu-id="ec7d6-182">Выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-182">Select **Apply**.</span></span>

4. <span data-ttu-id="ec7d6-183">Скопируйте URL-адрес проверки и поделитесь им с документацией администратора страниц LinkedIn на странице администратора страниц LinkedIn вашего [учебного заведения.](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admins-overview?lang=en)</span><span class="sxs-lookup"><span data-stu-id="ec7d6-183">Copy the verification URL and share it with your educational institution’s LinkedIn page admin [LinkedIn page admin documentation](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admins-overview?lang=en).</span></span> <span data-ttu-id="ec7d6-184">Срок действия ссылки для проверки истекает через 30 дней.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-184">The verification link expires after 30 days.</span></span>  

   ![Параметры linkedin для тренера по карьерной карьере](media/career-coach-linked-in.png)  

#### <a name="course-catalog"></a><span data-ttu-id="ec7d6-186">Каталог курса</span><span class="sxs-lookup"><span data-stu-id="ec7d6-186">Course catalog</span></span>

<span data-ttu-id="ec7d6-187">Каталог курсов представляет курсы и классы, предлагаемые учащимся учебным заведением.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-187">The course catalog represents the courses and classes offered to students by your educational institution.</span></span> <span data-ttu-id="ec7d6-188">Эти курсы используются в приложении в двух областях:</span><span class="sxs-lookup"><span data-stu-id="ec7d6-188">These courses are used within the app in two areas:</span></span>

- <span data-ttu-id="ec7d6-189">Курсы возвращаются как часть учебных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-189">Courses are returned as part of learning resources.</span></span>  

- <span data-ttu-id="ec7d6-190">Курсы и метаданные курса, например описания, используются для того, чтобы помочь учащимся определить свои навыки при отправке расшифровки.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-190">Courses and course meta data, like descriptions, are used to help students identify their skills when they upload a transcript.</span></span>  

<span data-ttu-id="ec7d6-191">Чтобы создать каталог курсов, составьте список всех курсов, которые вы преподаете в учебном заведении, и загрузите его в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-191">To create the course catalog, put together a list of all courses taught at your educational institution and upload it as a CSV file.</span></span> <span data-ttu-id="ec7d6-192">Приложение использует каталог курсов для определения навыков учащегося из его расшифровки и для определения курса.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-192">The app draws from the course catalog to identify a student’s skills from their transcript and to suggest courses to take.</span></span> 

##### <a name="course-catalog-documents-formatting-and-schema"></a><span data-ttu-id="ec7d6-193">Форматирование и схема документов каталога курсов</span><span class="sxs-lookup"><span data-stu-id="ec7d6-193">Course catalog documents formatting and schema</span></span>

<span data-ttu-id="ec7d6-194">Документ должен быть в формате CSV с максимальным размером 18 МБ.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-194">The document needs to be in CSV format with a maximum size of 18 MB.</span></span> <span data-ttu-id="ec7d6-195">Документ должен содержать обязательное название курса полей, его **ИД** и **URL-адрес курса.**</span><span class="sxs-lookup"><span data-stu-id="ec7d6-195">The document must contain the required fields **course title**, **course ID**, and **course URL**.</span></span> <span data-ttu-id="ec7d6-196">Включив рекомендуемые поля, вы повысите качество работы учащихся, возвращая более лучшие результаты поиска и определение навыков.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-196">Including the recommended fields improves the experience for students by returning better search results and skill identification.</span></span>

> [!NOTE]
> <span data-ttu-id="ec7d6-197">Начните с [образца документа каталога]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) курса, чтобы приступить к работе.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-197">Start with the [sample course catalog]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) document to get started.</span></span>

<span data-ttu-id="ec7d6-198">В следующей таблице показаны элементы, которые нужно включить в каталог курса:</span><span class="sxs-lookup"><span data-stu-id="ec7d6-198">The following table shows the items to include in the course catalog:</span></span>


| <span data-ttu-id="ec7d6-199">Имя</span><span class="sxs-lookup"><span data-stu-id="ec7d6-199">Name</span></span>             | <span data-ttu-id="ec7d6-200">Статус</span><span class="sxs-lookup"><span data-stu-id="ec7d6-200">Status</span></span>      | <span data-ttu-id="ec7d6-201">Тип</span><span class="sxs-lookup"><span data-stu-id="ec7d6-201">Type</span></span>   | <span data-ttu-id="ec7d6-202">Описание</span><span class="sxs-lookup"><span data-stu-id="ec7d6-202">Description</span></span>                                                                    |
|------------------|-------------|--------|--------------------------------------------------------------------------------|
| <span data-ttu-id="ec7d6-203">courseId</span><span class="sxs-lookup"><span data-stu-id="ec7d6-203">courseId</span></span>         | <span data-ttu-id="ec7d6-204">Обязательно</span><span class="sxs-lookup"><span data-stu-id="ec7d6-204">Required</span></span>    | <span data-ttu-id="ec7d6-205">Строка</span><span class="sxs-lookup"><span data-stu-id="ec7d6-205">string</span></span> | <span data-ttu-id="ec7d6-206">Обычно ид курса (как правило, он сопописается с тем, что создается в записи разговоров).</span><span class="sxs-lookup"><span data-stu-id="ec7d6-206">Usually the course id (Typically maps to what is generated in the transcript).</span></span> |
| <span data-ttu-id="ec7d6-207">Название</span><span class="sxs-lookup"><span data-stu-id="ec7d6-207">title</span></span>            | <span data-ttu-id="ec7d6-208">Обязательно</span><span class="sxs-lookup"><span data-stu-id="ec7d6-208">Required</span></span>    | <span data-ttu-id="ec7d6-209">Строка</span><span class="sxs-lookup"><span data-stu-id="ec7d6-209">string</span></span> | <span data-ttu-id="ec7d6-210">Обычно название курса.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-210">Usually the course title.</span></span>                                                      |
| <span data-ttu-id="ec7d6-211">sourceLink</span><span class="sxs-lookup"><span data-stu-id="ec7d6-211">sourceLink</span></span>       | <span data-ttu-id="ec7d6-212">Обязательно</span><span class="sxs-lookup"><span data-stu-id="ec7d6-212">Required</span></span>    | <span data-ttu-id="ec7d6-213">Url</span><span class="sxs-lookup"><span data-stu-id="ec7d6-213">URL</span></span>    | <span data-ttu-id="ec7d6-214">Ссылка веб-сайта на страницу курса.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-214">Website link to the course page.</span></span>                                               |
| <span data-ttu-id="ec7d6-215">Описание</span><span class="sxs-lookup"><span data-stu-id="ec7d6-215">description</span></span>      | <span data-ttu-id="ec7d6-216">Рекомендуется</span><span class="sxs-lookup"><span data-stu-id="ec7d6-216">Recommended</span></span> | <span data-ttu-id="ec7d6-217">Строка</span><span class="sxs-lookup"><span data-stu-id="ec7d6-217">string</span></span> | <span data-ttu-id="ec7d6-218">Вводный текст для курса.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-218">Introduction text for the course.</span></span>                                              |
| <span data-ttu-id="ec7d6-219">Язык</span><span class="sxs-lookup"><span data-stu-id="ec7d6-219">language</span></span>         | <span data-ttu-id="ec7d6-220">Рекомендуется</span><span class="sxs-lookup"><span data-stu-id="ec7d6-220">Recommended</span></span> | <span data-ttu-id="ec7d6-221">Строка</span><span class="sxs-lookup"><span data-stu-id="ec7d6-221">string</span></span> | <span data-ttu-id="ec7d6-222">Язык курса.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-222">Language of the course.</span></span> <span data-ttu-id="ec7d6-223">Используйте стандартные языковые коды.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-223">Use standard language codes.</span></span>                           |
| <span data-ttu-id="ec7d6-224">Формат</span><span class="sxs-lookup"><span data-stu-id="ec7d6-224">format</span></span>           | <span data-ttu-id="ec7d6-225">Рекомендуется</span><span class="sxs-lookup"><span data-stu-id="ec7d6-225">Recommended</span></span> | <span data-ttu-id="ec7d6-226">Строка</span><span class="sxs-lookup"><span data-stu-id="ec7d6-226">string</span></span> | <span data-ttu-id="ec7d6-227">Режим обучения, например, онлайн, видео, линлин.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-227">Mode of teaching, e.g., online, video, in-person.</span></span>                              |
| <span data-ttu-id="ec7d6-228">thumbnailLink</span><span class="sxs-lookup"><span data-stu-id="ec7d6-228">thumbnailLink</span></span>    | <span data-ttu-id="ec7d6-229">Рекомендуется</span><span class="sxs-lookup"><span data-stu-id="ec7d6-229">Recommended</span></span> | <span data-ttu-id="ec7d6-230">Url</span><span class="sxs-lookup"><span data-stu-id="ec7d6-230">URL</span></span>    | <span data-ttu-id="ec7d6-231">Ссылка эскиза на изображение курса.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-231">Thumbnail link to the course image.</span></span>                                            |
| <span data-ttu-id="ec7d6-232">thumbnailAltText</span><span class="sxs-lookup"><span data-stu-id="ec7d6-232">thumbnailAltText</span></span> | <span data-ttu-id="ec7d6-233">Рекомендуется</span><span class="sxs-lookup"><span data-stu-id="ec7d6-233">Recommended</span></span> | <span data-ttu-id="ec7d6-234">Строка</span><span class="sxs-lookup"><span data-stu-id="ec7d6-234">string</span></span> | <span data-ttu-id="ec7d6-235">Заме доступа к изображению</span><span class="sxs-lookup"><span data-stu-id="ec7d6-235">Accessibility alt text for the image</span></span>                                           |
| <span data-ttu-id="ec7d6-236">educationLevel</span><span class="sxs-lookup"><span data-stu-id="ec7d6-236">educationLevel</span></span>   | <span data-ttu-id="ec7d6-237">Рекомендуется</span><span class="sxs-lookup"><span data-stu-id="ec7d6-237">Recommended</span></span> | <span data-ttu-id="ec7d6-238">Строка</span><span class="sxs-lookup"><span data-stu-id="ec7d6-238">string</span></span> | <span data-ttu-id="ec7d6-239">Учебный уровень, пример.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-239">Study level, ex.</span></span> <span data-ttu-id="ec7d6-240">Студент-выпускник.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-240">Undergraduate/Graduate.</span></span>                                       |
| <span data-ttu-id="ec7d6-241">Темы</span><span class="sxs-lookup"><span data-stu-id="ec7d6-241">topics</span></span>           | <span data-ttu-id="ec7d6-242">Рекомендуется</span><span class="sxs-lookup"><span data-stu-id="ec7d6-242">Recommended</span></span> | <span data-ttu-id="ec7d6-243">Строка</span><span class="sxs-lookup"><span data-stu-id="ec7d6-243">string</span></span> | <span data-ttu-id="ec7d6-244">Темы и теги, связанные с навыками, которые преподаются в курсах.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-244">Topics or tags that are associated with the skills the courses teach.</span></span>          |

##### <a name="add-the-course-catalog"></a><span data-ttu-id="ec7d6-245">Добавление каталога курса</span><span class="sxs-lookup"><span data-stu-id="ec7d6-245">Add the course catalog</span></span>

1. <span data-ttu-id="ec7d6-246">Во sign in to the **Teams admin center**.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-246">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="ec7d6-247">Выберите Teams **приложения** &gt; **Manage apps** Career &gt; **Coach** &gt; **Параметры** &gt; **course catalog**.  </span><span class="sxs-lookup"><span data-stu-id="ec7d6-247">Select **Teams apps** &gt; **Manage apps** &gt; **Career Coach** &gt; **Settings** &gt;  **Course catalog**.</span></span>

2. <span data-ttu-id="ec7d6-248">Upload курсы в формате CSV.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-248">Upload courses in CSV format.</span></span>

4. <span data-ttu-id="ec7d6-249">Выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-249">Select **Apply**.</span></span>

   ![Раздел каталога курса приложения "Тренер по карьерной карьере"](media/course-catalog.png)

#### <a name="fields-of-study"></a><span data-ttu-id="ec7d6-251">Поля исследования</span><span class="sxs-lookup"><span data-stu-id="ec7d6-251">Fields of study</span></span>

<span data-ttu-id="ec7d6-252">Поля исследования являются синонимами с основными областями интересов, академическими и градусами.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-252">The fields of study are synonymous with major areas of interest, academic major, and degree.</span></span> <span data-ttu-id="ec7d6-253">На эти названия ссылается студент, когда он начинает использовать приложение и настраивает свой персонализированный профиль.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-253">These titles are referenced by students when they start using the app and begin setting up their personalized profile.</span></span>

<span data-ttu-id="ec7d6-254">Добавьте все поля обучения, доступные учащимся, например инженерные, английский, бизнес и так далее.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-254">Add all fields of study available to students such as Engineering, English, Business, and so on.</span></span> <span data-ttu-id="ec7d6-255">Список полей позволяет учащимся найти интересуют их поля и добавить в свой профиль область фокуса.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-255">The list of fields lets students discover fields of study that may interest them and add their area of focus to their profile.</span></span>

> [!NOTE]
> <span data-ttu-id="ec7d6-256">Начните с [примера поля документа.](https://aka.ms/career-coach/docs/it-admins/sample-fieldsofstudy)</span><span class="sxs-lookup"><span data-stu-id="ec7d6-256">Start with the [sample field of study](https://aka.ms/career-coach/docs/it-admins/sample-fieldsofstudy) document.</span></span>
##### <a name="add-the-fields-of-study"></a><span data-ttu-id="ec7d6-257">Добавление полей исследования</span><span class="sxs-lookup"><span data-stu-id="ec7d6-257">Add the fields of study</span></span>

1. <span data-ttu-id="ec7d6-258">Во sign in to the **Teams admin center**.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-258">Sign in to the **Teams admin center**.</span></span>
1. <span data-ttu-id="ec7d6-259">Выберите **Teams приложения Manage** &gt; **apps** Career &gt; **Coach** &gt; **Параметры** Fields of Study &gt; (Поля **обучения).**  </span><span class="sxs-lookup"><span data-stu-id="ec7d6-259">Select **Teams apps** &gt; **Manage apps** &gt; **Career Coach** &gt; **Settings** &gt;  **Fields of study**.</span></span>

2. <span data-ttu-id="ec7d6-260">Upload в формате CSV.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-260">Upload field of study in CSV format.</span></span>

3. <span data-ttu-id="ec7d6-261">Выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-261">Select **Apply**.</span></span>

#### <a name="customization"></a><span data-ttu-id="ec7d6-262">Настройки</span><span class="sxs-lookup"><span data-stu-id="ec7d6-262">Customization</span></span>

<span data-ttu-id="ec7d6-263">Тренера по карьерной карьере можно настроить так, чтобы он был уникальным для вашего образовательного учреждения.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-263">Career Coach can be customized to be unique to your educational institution.</span></span> <span data-ttu-id="ec7d6-264">Настройка поддерживает добавление новых функций на панель мониторинга.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-264">The customization supports adding experiences to the dashboard.</span></span> <span data-ttu-id="ec7d6-265">Рекомендуется добавлять ссылки на доски вакансий, мероприятия, офис служб по карьерной работе, мероприятия, связанные с карьерой, клубы учащихся и другие ресурсы, которые помогают учащимся получить реальный опыт.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-265">It's recommended to add links to job boards, events, career services office, career-related events, student clubs, and any other resources that help students gain real-world experience.</span></span>

##### <a name="add-customized-experiences"></a><span data-ttu-id="ec7d6-266">Добавление настраиваемых функций</span><span class="sxs-lookup"><span data-stu-id="ec7d6-266">Add customized experiences</span></span>

1. <span data-ttu-id="ec7d6-267">Во sign in to the **Teams admin center**.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-267">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="ec7d6-268">Выберите Teams **приложения Управление** &gt; **приложениями** &gt; **Coach для**  >  **Параметры** &gt; **настройки**.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-268">Select **Teams apps** &gt; **Manage apps** &gt; **Career Coach** > **Settings** &gt; **Customization**.</span></span>

2. <span data-ttu-id="ec7d6-269">Добавьте каждый URL-адрес, заголовок и краткое описание.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-269">Add each URL, a title, and short description.</span></span>  
  
3. <span data-ttu-id="ec7d6-270">Выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-270">Select **Apply**.</span></span>

## <a name="making-career-coach-available-to-your-organization"></a><span data-ttu-id="ec7d6-271">Как сделать тренера по карьерной карьере доступным для вашей организации</span><span class="sxs-lookup"><span data-stu-id="ec7d6-271">Making Career Coach available to your organization</span></span>

<span data-ttu-id="ec7d6-272">Теперь, когда для вашей организации настроен тренер по карьерной карьере.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-272">Now that Career Coach has been configured for your organization.</span></span> <span data-ttu-id="ec7d6-273">Выполните эти действия, чтобы гарантировать, что тренер по карьерной деятельности доступен для организации в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-273">Follow these steps to ensure that Career Coach is available to organization in Microsoft Teams.</span></span>

### <a name="enable-the-app"></a><span data-ttu-id="ec7d6-274">Включить приложение</span><span class="sxs-lookup"><span data-stu-id="ec7d6-274">Enable the app</span></span>

<span data-ttu-id="ec7d6-275">После завершения настройки в включить приложение для учащихся и лицензированных пользователей, чтобы они могли получить доступ к тренеру по карьерной карьере.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-275">After you complete the configuration, enable the app for students and licensed users so they'll have access to Career Coach.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ec7d6-276">У вас должны быть разрешения глобального Teams роли администратора.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-276">You must have Global or Teams admin role permissions.</span></span>

1. <span data-ttu-id="ec7d6-277">Во sign in to the **Teams admin center**.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-277">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="ec7d6-278">Выберите Teams **приложения Manage** &gt; **apps** &gt; **Career Coach**.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-278">Select **Teams apps** &gt; **Manage apps** &gt; **Career Coach**.</span></span>

2. <span data-ttu-id="ec7d6-279">Переместить в положение Разрешено положение **состояние**.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-279">Move the Status toggle to **Allowed**.</span></span>  

  > [!NOTE]
  > <span data-ttu-id="ec7d6-280">Разрешено означает, что приложение доступно для пользователей в вашем учебном заведении.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-280">Allowed means that the app is available for users in your educational institution.</span></span> <span data-ttu-id="ec7d6-281">Заблокировано означает, что приложение не доступно учащимся.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-281">Blocked means that the app isn't available to students.</span></span>

### <a name="add-career-coach-as-an-installed-app"></a><span data-ttu-id="ec7d6-282">Добавление тренера по карьерной карьере в качестве установленного приложения</span><span class="sxs-lookup"><span data-stu-id="ec7d6-282">Add Career Coach as an installed app</span></span>

> [!NOTE]
> <span data-ttu-id="ec7d6-283">Это гарантирует, что 1) правильно настроен тренер по карьерной деятельности для вашей организации 2), что учащиеся находят тренера по карьерной карьере.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-283">This step ensures 1) that Career Coach is properly configured for your organization 2) that students find Career Coach.</span></span>

1. <span data-ttu-id="ec7d6-284">Во sign in to the **Teams admin center**.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-284">Sign in to the **Teams admin center**.</span></span>

2. <span data-ttu-id="ec7d6-285">Выберите **Teams политики установки** приложений &gt; **Ваша** &gt; *политика*.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-285">Select **Teams apps** &gt;**Setup policies** &gt; *Your policy*.</span></span> 

3. <span data-ttu-id="ec7d6-286">В области Установленные приложения выберите Добавить приложения.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-286">Under Installed apps, select Add apps.</span></span>

4. <span data-ttu-id="ec7d6-287">В области Добавить установленные приложения найщите приложения, которые вы хотите автоматически установить для пользователей при Teams.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-287">In the Add installed apps pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="ec7d6-288">Вы также можете фильтровать приложения с помощью политики разрешений приложений.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-288">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="ec7d6-289">Выбрав список приложений, выберите Добавить.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-289">When you've chosen your list of apps, select Add.</span></span>

### <a name="pin-the-app"></a><span data-ttu-id="ec7d6-290">Закрепление приложения</span><span class="sxs-lookup"><span data-stu-id="ec7d6-290">Pin the app</span></span>

<span data-ttu-id="ec7d6-291">Закрепление тренера по карьерной деятельности сделает приложение более доступным и видимым для учащихся.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-291">Pinning Career Coach will make the app more accessible and visible for students.</span></span>

1. <span data-ttu-id="ec7d6-292">Во sign in to the **Teams admin center**.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-292">Sign in to the **Teams admin center**.</span></span>

2. <span data-ttu-id="ec7d6-293">Выберите **Teams политики установки** приложений &gt; **Ваша** &gt; *политика*.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-293">Select **Teams apps** &gt;**Setup policies** &gt; *Your policy*.</span></span> 

3. <span data-ttu-id="ec7d6-294">В **области Закрепленные приложения** выберите Добавить **приложения**.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-294">Under **Pinned apps**, choose **Add apps**.</span></span>

4. <span data-ttu-id="ec7d6-295">Найщите **тренера по карьерной карьере,** а затем выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-295">Search for **Career Coach**, and then select **Add**.</span></span>

5. <span data-ttu-id="ec7d6-296">Выберите порядок появления приложения и выберите **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-296">Choose the order for the app to appear and select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="ec7d6-297">Учащиеся будут уведомлены в Microsoft Teams о том, что тренер по карьерной деятельности закреплен.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-297">Students will be notified in Microsoft Teams that Career Coach has been pinned.</span></span>

<span data-ttu-id="ec7d6-298">Дополнительные [сведения можно и здесь:](/microsoftteams/teams-app-setup-policies) Управление политиками настройки приложений в Корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ec7d6-298">Reference [Manage app setup policies in Microsoft](/microsoftteams/teams-app-setup-policies) for additional details.</span></span>

## <a name="resources"></a><span data-ttu-id="ec7d6-299">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="ec7d6-299">Resources</span></span>

<span data-ttu-id="ec7d6-300">Следующие ресурсы помогут вам спланировать приложение "Тренер по карьерной карьере".</span><span class="sxs-lookup"><span data-stu-id="ec7d6-300">The following resources will help you plan your Career Coach app.</span></span>

- [<span data-ttu-id="ec7d6-301">Знакомство с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ec7d6-301">Welcome to Microsoft Teams</span></span>](Teams-overview.md)

- [<span data-ttu-id="ec7d6-302">Способ развертывания Teams</span><span class="sxs-lookup"><span data-stu-id="ec7d6-302">How to roll out Teams</span></span>](get-started-with-teams-resources-for-org-wide-rollout.md?tabs=SmallBusiness)

- [<span data-ttu-id="ec7d6-303">Обзор команд и каналов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ec7d6-303">Overview of teams and channels in Microsoft Teams</span></span>](teams-channels-overview.md)

- [<span data-ttu-id="ec7d6-304">Управление приложениями в Центре Microsoft Teams администрирования</span><span class="sxs-lookup"><span data-stu-id="ec7d6-304">Managing apps in Microsoft Teams Admin Center</span></span>](manage-apps.md)

- [<span data-ttu-id="ec7d6-305">Набор виртуальных ориентаций в Интернете</span><span class="sxs-lookup"><span data-stu-id="ec7d6-305">Online Virtual Orientation Kit</span></span>](https://www.microsoft.com/education/remote-learning/virtual-orientation) 

- [<span data-ttu-id="ec7d6-306">Ограничения и спецификация Teams каналов</span><span class="sxs-lookup"><span data-stu-id="ec7d6-306">Limits and specification of Teams channels</span></span>](limits-specifications-teams.md)

- [<span data-ttu-id="ec7d6-307">Начало работы с обучением администраторов Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ec7d6-307">Getting started with admin training for Microsoft Teams</span></span>](ITAdmin-readiness.md)

- [<span data-ttu-id="ec7d6-308">Устранение неисправностей Teams</span><span class="sxs-lookup"><span data-stu-id="ec7d6-308">Teams troubleshooting</span></span>](/microsoftteams/troubleshoot/teams-welcome)

- [<span data-ttu-id="ec7d6-309">Управление политиками разрешений для приложений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ec7d6-309">Manage app permission policies in Microsoft Teams</span></span>](teams-app-permission-policies.md)
