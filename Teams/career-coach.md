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
description: Узнайте, как приобрести, настроить и включить для тренера по Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9911f880ba817afff10acb2a347a5c8c776d059c
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130089"
---
# <a name="purchase-configure-and-enable-career-coach-for-microsoft-teams"></a><span data-ttu-id="b1768-103">Приобрести, настроить и включить для тренеров по Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b1768-103">Purchase, configure, and enable Career Coach for Microsoft Teams</span></span>

<span data-ttu-id="b1768-104">Career Coach — это приложение Microsoft Teams для образовательных сфере, которое работает на сайте LinkedIn и предоставляет учащимся более высокого уровня персонализированные рекомендации по переходу к карьере.</span><span class="sxs-lookup"><span data-stu-id="b1768-104">Career Coach is a Microsoft Teams for Education app powered by LinkedIn that provides personalized guidance for higher education students to navigate their career journey.</span></span> <span data-ttu-id="b1768-105">Тренер по карьерной подготовке — это единое решение для профессиональной карьеры учащихся, которое позволяет им познать свой путь к карьере, развивать реальные навыки и строить свою сеть в одном месте.</span><span class="sxs-lookup"><span data-stu-id="b1768-105">Career Coach offers educational institutions a unified career solution for students to discover their career path, grow real-world skills, and build their network all in one place.</span></span>

<span data-ttu-id="b1768-106">Подробнее о [тренере по карьерной карьере.](https://aka.ms/career-coach)</span><span class="sxs-lookup"><span data-stu-id="b1768-106">Learn more about [Career Coach](https://aka.ms/career-coach).</span></span>

> [!NOTE]
> <span data-ttu-id="b1768-107">Используйте рекомендации и полезные советы из этого руководства, чтобы включить возможности тренера по карьерной карьере для студентов, преподавателей и сотрудников.</span><span class="sxs-lookup"><span data-stu-id="b1768-107">Use the best practices and helpful tips in this guide to enable the capabilities of Career Coach for students, faculty, and staff.</span></span> <span data-ttu-id="b1768-108">См. [статью Краткое руководство по планированию.](https://support.microsoft.com/office/c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4)</span><span class="sxs-lookup"><span data-stu-id="b1768-108">See the [Quick planning guide](https://support.microsoft.com/office/c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4) article.</span></span>

## <a name="review-the-requirements"></a><span data-ttu-id="b1768-109">Проверка требований</span><span class="sxs-lookup"><span data-stu-id="b1768-109">Review the requirements</span></span>

<span data-ttu-id="b1768-110">Чтобы включить для вашего учебного заведения функцию "Тренер по карьерной работе", просмотрите, что нужно для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="b1768-110">To enable Career Coach for your educational institution, review what you need to get the app up and running.</span></span>

<span data-ttu-id="b1768-111">**Технические требования**</span><span class="sxs-lookup"><span data-stu-id="b1768-111">**Technical requirements**</span></span>

  - <span data-ttu-id="b1768-112">Office 365 клиента с Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b1768-112">Office 365 tenant with Azure Active Directory</span></span>

  - <span data-ttu-id="b1768-113">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b1768-113">Microsoft Teams</span></span>

  - <span data-ttu-id="b1768-114">Подключения учетной записи LinkedIn в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b1768-114">LinkedIn account connections in Azure Active Directory</span></span>

<span data-ttu-id="b1768-115">**Лицензии**</span><span class="sxs-lookup"><span data-stu-id="b1768-115">**Licenses**</span></span>

  - <span data-ttu-id="b1768-116">Факультет</span><span class="sxs-lookup"><span data-stu-id="b1768-116">Faculty</span></span> 

  - <span data-ttu-id="b1768-117">Студентов</span><span class="sxs-lookup"><span data-stu-id="b1768-117">Students</span></span>

> [!NOTE]
> <span data-ttu-id="b1768-118">ИТ-администратору, заполняющий конфигурацию, должна быть назначена лицензия преподавателя по карьерной карьере.</span><span class="sxs-lookup"><span data-stu-id="b1768-118">A Career Coach Faculty license must be assigned to the IT admin completing the configuration.</span></span>

<span data-ttu-id="b1768-119">**Данные и файлы из вашего образовательного учреждения**</span><span class="sxs-lookup"><span data-stu-id="b1768-119">**Data and files from your educational institution**</span></span>

  - <span data-ttu-id="b1768-120">Данные каталога курса</span><span class="sxs-lookup"><span data-stu-id="b1768-120">Course catalog data</span></span>

  - <span data-ttu-id="b1768-121">Предлагаемые поля исследования</span><span class="sxs-lookup"><span data-stu-id="b1768-121">Fields of study offered</span></span>

  - <span data-ttu-id="b1768-122">Страница LinkedIn учебного заведения</span><span class="sxs-lookup"><span data-stu-id="b1768-122">Educational institution’s LinkedIn page</span></span>

  - <span data-ttu-id="b1768-123">Подписка на LinkedIn Learning для учебного заведения (предпочитаемая)</span><span class="sxs-lookup"><span data-stu-id="b1768-123">LinkedIn Learning campus subscription (preferred)</span></span>

## <a name="purchase-the-career-coach-licenses"></a><span data-ttu-id="b1768-124">Приобретение лицензий для тренера по карьерной деятельности</span><span class="sxs-lookup"><span data-stu-id="b1768-124">Purchase the Career Coach licenses</span></span>

<span data-ttu-id="b1768-125">Тренер по карьерной подготовке доступен по всему миру (за исключением Китая и России) для квалифицированных высших учебных заведений с помощью регистрации решений для образовательных учреждений (EES), поставщиков облачных услуг (CSP) и Microsoft 365 администрирования (прямой веб-сайт).</span><span class="sxs-lookup"><span data-stu-id="b1768-125">Career Coach is available worldwide (except China and Russia) for qualified higher education institutions through Enrollment for Education Solutions (EES), Cloud Service Providers (CSP), and Microsoft 365 admin center (web direct).</span></span> <span data-ttu-id="b1768-126">Как приложение Microsoft Teams, клиенты должны Microsoft 365 A3/A5 или Office 365 A1/A3/A5.</span><span class="sxs-lookup"><span data-stu-id="b1768-126">As a Microsoft Teams app, customers must have Microsoft 365 A3/A5 or Office 365 A1/A3/A5.</span></span>

### <a name="assign-app-licenses-to-users"></a><span data-ttu-id="b1768-127">Назначение лицензий на приложения пользователям</span><span class="sxs-lookup"><span data-stu-id="b1768-127">Assign app licenses to users</span></span>

<span data-ttu-id="b1768-128">Пошаговую инструкцию см. в инструкциях по [назначению лицензий пользователям.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="b1768-128">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="turn-on-linkedin-account-connections"></a><span data-ttu-id="b1768-129">Включить подключения к учетной записи LinkedIn</span><span class="sxs-lookup"><span data-stu-id="b1768-129">Turn on LinkedIn account connections</span></span>

<span data-ttu-id="b1768-130">Тренер по **карьерной карьере** требует от пользователей учебного заведения возможности подключать свою учетную запись Microsoft 365 к своей учетной записи LinkedIn, которая упростилась в рамках тренера по карьерной карьере</span><span class="sxs-lookup"><span data-stu-id="b1768-130">Career Coach **requires** your educational institution’s users to have the ability to connect their Microsoft 365 account to their LinkedIn account that is facilitated within Career Coach</span></span>

1. <span data-ttu-id="b1768-131">Во войти в [Центр администрирования Azure AD](https://aad.portal.azure.com/) можно с помощью учетной записи, которая является глобальным администратором организации Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b1768-131">Sign in to the [Azure AD admin center](https://aad.portal.azure.com/) with an account that's a global admin for the Azure AD organization.</span></span>

2. <span data-ttu-id="b1768-132">Выберите **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="b1768-132">Select **Users**.</span></span>

3. <span data-ttu-id="b1768-133">На странице **Пользователи** выберите **Параметры пользователя**.</span><span class="sxs-lookup"><span data-stu-id="b1768-133">On the **Users** page, select **User settings**.</span></span>

4. <span data-ttu-id="b1768-134">В **области Подключения к учетной записи LinkedIn** разрешить пользователям подключать свои учетные записи для доступа к своим подключениям LinkedIn в некоторых приложениях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b1768-134">Under **LinkedIn account connections**, allow users to connect their accounts to access their LinkedIn connections within some Microsoft apps.</span></span> <span data-ttu-id="b1768-135">Никакие данные не делиться, пока пользователи не согласится подключить свои учетные записи.</span><span class="sxs-lookup"><span data-stu-id="b1768-135">No data is shared until users consent to connect their accounts.</span></span>

   - <span data-ttu-id="b1768-136">Выберите **Да,** чтобы включить службу для всех пользователей в учебном заведении</span><span class="sxs-lookup"><span data-stu-id="b1768-136">Select **Yes** to enable the service for all users in your educational institution</span></span>

   - <span data-ttu-id="b1768-137">Выберите **выбранную группу,** чтобы включить службу только для группы выбранных пользователей в вашем образовательном учреждении</span><span class="sxs-lookup"><span data-stu-id="b1768-137">Select **Selected group** to enable the service for only a group of selected users in your educational institution</span></span>

   - <span data-ttu-id="b1768-138">Выберите **Нет,** чтобы отозвать согласие всех пользователей в вашем образовательном учреждении</span><span class="sxs-lookup"><span data-stu-id="b1768-138">Select **No** to withdraw consent from all users in your educational institution</span></span>

<span data-ttu-id="b1768-139">Узнайте, как [интегрировать подключения учетной записи LinkedIn в Azure Active Directory](/azure/active-directory/enterprise-users/linkedin-integration)</span><span class="sxs-lookup"><span data-stu-id="b1768-139">Learn how to [Integrate LinkedIn account connections in Azure Active Directory](/azure/active-directory/enterprise-users/linkedin-integration)</span></span>

## <a name="configure-career-coach-in-the-teams-admin-center"></a><span data-ttu-id="b1768-140">Настройка тренера по карьерной Teams центре администрирования</span><span class="sxs-lookup"><span data-stu-id="b1768-140">Configure Career Coach in the Teams admin center</span></span>

<span data-ttu-id="b1768-141">Используя параметры администратора в Центре Microsoft Teams, вы можете настроить его для своего учебного заведения и включить для пользователей.</span><span class="sxs-lookup"><span data-stu-id="b1768-141">Using the admin settings in the Microsoft Teams admin center, you can configure Career Coach for your educational institution and enable it for users.</span></span>

## <a name="access-the-career-coach-app-settings"></a><span data-ttu-id="b1768-142">Доступ к настройкам приложения "Тренер по карьерной карьере"</span><span class="sxs-lookup"><span data-stu-id="b1768-142">Access the Career Coach app settings</span></span>

<span data-ttu-id="b1768-143">На странице [Управление приложениями](/microsoftteams/manage-apps) можно просмотреть Teams приложений в каталоге приложений учебного заведения.</span><span class="sxs-lookup"><span data-stu-id="b1768-143">Use the [Manage apps page](/microsoftteams/manage-apps) to view the Teams apps in your educational institution’s app catalog.</span></span>

1. <span data-ttu-id="b1768-144">Во sign in to the **Teams admin center**.</span><span class="sxs-lookup"><span data-stu-id="b1768-144">Sign in to the **Teams admin center**.</span></span>

2. <span data-ttu-id="b1768-145">В левой области навигации выберите Teams **приложения Управление**  >  **приложениями**.</span><span class="sxs-lookup"><span data-stu-id="b1768-145">In the left navigation, select **Teams apps** > **Manage apps**.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="b1768-146">Для доступа к странице необходимо быть глобальным Teams администратором службы.</span><span class="sxs-lookup"><span data-stu-id="b1768-146">You must be a global admin or Teams service admin to access the page.</span></span>

3. <span data-ttu-id="b1768-147">Поиск или поиск по **запросу Тренер по карьерной работе**.</span><span class="sxs-lookup"><span data-stu-id="b1768-147">Search or browse for **Career Coach**.</span></span>  

4. <span data-ttu-id="b1768-148">Выберите **Тренер по карьерной деятельности**, а затем выберите **Параметры.**</span><span class="sxs-lookup"><span data-stu-id="b1768-148">Select **Career Coach**, and then select **Settings.**</span></span>  

    ![Приложение "Тренер по карьерной деятельности", выбранное с параметром Параметры с отображением](media/app-settings.png)

### <a name="configure-the-career-coach-app-settings"></a><span data-ttu-id="b1768-150">Настройка параметров приложения "Тренер по карьерной карьере"</span><span class="sxs-lookup"><span data-stu-id="b1768-150">Configure the Career Coach app settings</span></span>

<span data-ttu-id="b1768-151">У тренера есть пять категорий конфигураций:</span><span class="sxs-lookup"><span data-stu-id="b1768-151">Career Coach has five configuration categories:</span></span>

- [<span data-ttu-id="b1768-152">Торговая марка и настройки</span><span class="sxs-lookup"><span data-stu-id="b1768-152">Brand and preferences</span></span>](#brand-and-preferences)

- [<span data-ttu-id="b1768-153">Конфигурация LinkedIn</span><span class="sxs-lookup"><span data-stu-id="b1768-153">LinkedIn configuration</span></span>](#linkedin-configuration)

- [<span data-ttu-id="b1768-154">Каталог курса</span><span class="sxs-lookup"><span data-stu-id="b1768-154">Course catalog</span></span>](#course-catalog)

- [<span data-ttu-id="b1768-155">Поля исследования</span><span class="sxs-lookup"><span data-stu-id="b1768-155">Fields of study</span></span>](#fields-of-study)

- [<span data-ttu-id="b1768-156">Настройки</span><span class="sxs-lookup"><span data-stu-id="b1768-156">Customization</span></span>](#customization)

> [!NOTE]
> <span data-ttu-id="b1768-157">Чтобы эффективно включить приложение для студентов, преподавателей и  сотрудников, необходимы фирменная марка и параметры, конфигурация LinkedIn, каталог курса и поля обучения.</span><span class="sxs-lookup"><span data-stu-id="b1768-157">Brand and preferences, LinkedIn configuration, Course catalog, and Fields of study are **required** to effectively enable the app for students, faculty, and staff.</span></span>

#### <a name="brand-and-preferences"></a><span data-ttu-id="b1768-158">Торговая марка и настройки</span><span class="sxs-lookup"><span data-stu-id="b1768-158">Brand and preferences</span></span>

<span data-ttu-id="b1768-159">Задайте название, логотип и язык по умолчанию учебного заведения на странице параметров и фирменой символики.</span><span class="sxs-lookup"><span data-stu-id="b1768-159">Set your educational institution’s name, logo, and default language on the brand and preferences settings page.</span></span>

![Раздел фирменой марки «Тренер по карьерной карьере» в Центре администрирования](media/brand-preferences.png)

##### <a name="educational-institution-icon"></a><span data-ttu-id="b1768-161">Значок образовательного учреждения</span><span class="sxs-lookup"><span data-stu-id="b1768-161">Educational institution icon</span></span>

<span data-ttu-id="b1768-162">Значок учебного заведения используется во всем приложении "Тренер по карьерной деятельности", чтобы идентифицировать содержимое, уникальное для вашего учебного заведения, ресурсы каталога курсов во всем приложении и в разделе реальных функций панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="b1768-162">The educational institution icon is used throughout Career Coach to identify content unique to your educational institution, course catalog resources throughout the app, and on the real-world experiences section of the dashboard.</span></span> <span data-ttu-id="b1768-163">Значок лучше всего отформатирован как:</span><span class="sxs-lookup"><span data-stu-id="b1768-163">The icon is best formatted as:</span></span>

 - <span data-ttu-id="b1768-164">Прозрачный PNG</span><span class="sxs-lookup"><span data-stu-id="b1768-164">A transparent PNG</span></span>
 - <span data-ttu-id="b1768-165">Пропорции 1:1</span><span class="sxs-lookup"><span data-stu-id="b1768-165">Aspect ratio of 1:1</span></span>
 - <span data-ttu-id="b1768-166">Максимальный размер: 64 px x 64 px.</span><span class="sxs-lookup"><span data-stu-id="b1768-166">Maximum size of 64 px x 64 px.</span></span>

##### <a name="educational-institution-thumbnail"></a><span data-ttu-id="b1768-167">Эскиз образовательного учреждения</span><span class="sxs-lookup"><span data-stu-id="b1768-167">Educational institution thumbnail</span></span>

<span data-ttu-id="b1768-168">Значок учебного заведения будет использоваться для ресурсов каталога курсов во всем приложении, если определенное изображение не доступно для курса.</span><span class="sxs-lookup"><span data-stu-id="b1768-168">The educational institution icon will be used for course catalog resources throughout the app when a specific image isn't available for a course.</span></span> <span data-ttu-id="b1768-169">Значок лучше всего отформатирован как:</span><span class="sxs-lookup"><span data-stu-id="b1768-169">The icon is best formatted as:</span></span>

- <span data-ttu-id="b1768-170">A PNG</span><span class="sxs-lookup"><span data-stu-id="b1768-170">A PNG</span></span>
- <span data-ttu-id="b1768-171">Пропорции 16:9</span><span class="sxs-lookup"><span data-stu-id="b1768-171">Aspect ratio of 16:9</span></span>
- <span data-ttu-id="b1768-172">Максимальный размер: 360 px x 200 px.</span><span class="sxs-lookup"><span data-stu-id="b1768-172">Maximum size of 360 px x 200 px.</span></span>

#### <a name="linkedin-configuration"></a><span data-ttu-id="b1768-173">Конфигурация LinkedIn</span><span class="sxs-lookup"><span data-stu-id="b1768-173">LinkedIn configuration</span></span>

<span data-ttu-id="b1768-174">Конфигурация LinkedIn связывает Тренера по карьерной деятельности с данными общедоступных выпускников из LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="b1768-174">The LinkedIn configuration connects Career Coach with public alumni data from LinkedIn.</span></span>

> [!NOTE]
> <span data-ttu-id="b1768-175">Невозможно включить тренера по карьерной карьере без проверки подключения к странице LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="b1768-175">Career Coach can't be enabled without the LinkedIn page connection verified.</span></span>

##### <a name="add-and-confirm-the-linkedin-page"></a><span data-ttu-id="b1768-176">Добавление и подтверждение страницы LinkedIn</span><span class="sxs-lookup"><span data-stu-id="b1768-176">Add and confirm the LinkedIn page</span></span>

<span data-ttu-id="b1768-177">Определите страницу LinkedIn учебного заведения.</span><span class="sxs-lookup"><span data-stu-id="b1768-177">Determine the educational institution's LinkedIn page.</span></span> <span data-ttu-id="b1768-178">Найдите страницу LinkedIn, вы можете найти ее в LinkedIn или связаться с сотрудником, который является сотрудником службы по карьерной карьере, чтобы определить правильную страницу.</span><span class="sxs-lookup"><span data-stu-id="b1768-178">Find the LinkedIn page by searching on LinkedIn or connecting with a career services staff member to determine the correct page to use.</span></span>  
  
1. <span data-ttu-id="b1768-179">Во sign in to the **Teams admin center**.</span><span class="sxs-lookup"><span data-stu-id="b1768-179">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="b1768-180">Выберите Teams **приложения Управление**  >  **приложениями**  >  **Подключение к LinkedIn Для**  >  **тренеров по карьерной карьере**.</span><span class="sxs-lookup"><span data-stu-id="b1768-180">Select **Teams apps** > **Manage apps** > **Career Coach** > **LinkedIn connection**.</span></span>

2. <span data-ttu-id="b1768-181">Введите URL-адрес страницы LinkedIn учебного заведения.</span><span class="sxs-lookup"><span data-stu-id="b1768-181">Enter your educational institution's LinkedIn page URL.</span></span>  

3. <span data-ttu-id="b1768-182">Выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="b1768-182">Select **Apply**.</span></span>

4. <span data-ttu-id="b1768-183">Скопируйте URL-адрес проверки и поделитесь им с документацией администратора страниц LinkedIn на странице администратора страниц LinkedIn вашего [учебного заведения.](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admins-overview?lang=en)</span><span class="sxs-lookup"><span data-stu-id="b1768-183">Copy the verification URL and share it with your educational institution’s LinkedIn page admin [LinkedIn page admin documentation](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admins-overview?lang=en).</span></span> <span data-ttu-id="b1768-184">Срок действия ссылки для проверки истекает через 30 дней.</span><span class="sxs-lookup"><span data-stu-id="b1768-184">The verification link expires after 30 days.</span></span>  

   ![Linkedin settings for the career coach](media/linkedin.png)  

#### <a name="course-catalog"></a><span data-ttu-id="b1768-186">Каталог курса</span><span class="sxs-lookup"><span data-stu-id="b1768-186">Course catalog</span></span>

<span data-ttu-id="b1768-187">Каталог курсов представляет курсы и классы, предлагаемые учащимся учебным заведением.</span><span class="sxs-lookup"><span data-stu-id="b1768-187">The course catalog represents the courses and classes offered to students by your educational institution.</span></span> <span data-ttu-id="b1768-188">Эти курсы используются в приложении в двух областях:</span><span class="sxs-lookup"><span data-stu-id="b1768-188">These courses are used within the app in two areas:</span></span>

- <span data-ttu-id="b1768-189">Курсы возвращаются как часть учебных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b1768-189">Courses are returned as part of learning resources.</span></span>  

- <span data-ttu-id="b1768-190">Курсы и метаданные курса, например описания, используются для того, чтобы помочь учащимся определить свои навыки при отправке расшифровки.</span><span class="sxs-lookup"><span data-stu-id="b1768-190">Courses and course meta data, like descriptions, are used to help students identify their skills when they upload a transcript.</span></span>  

<span data-ttu-id="b1768-191">Чтобы создать каталог курсов, составьте список всех курсов, которые вы преподаете в учебном заведении, и загрузите его в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="b1768-191">To create the course catalog, put together a list of all courses taught at your educational institution and upload it as a CSV file.</span></span> <span data-ttu-id="b1768-192">Приложение использует каталог курсов, чтобы определить навыки учащегося из его расшифровки и предложить курсы.</span><span class="sxs-lookup"><span data-stu-id="b1768-192">The app draws from the course catalog to identify a student’s skills from their transcript and to suggest courses to take.</span></span> 

> [!NOTE]
> <span data-ttu-id="b1768-193">Сведения [о защите сведений](location-of-data-in-teams.md) об [](security-compliance-overview.md) учащихся см. в Teams безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="b1768-193">See [Location of data in Teams](location-of-data-in-teams.md) and [Security and compliance](security-compliance-overview.md) for information about protecting of student information.</span></span> 

##### <a name="course-catalog-documents-formatting-and-schema"></a><span data-ttu-id="b1768-194">Форматирование и схема документов каталога курсов</span><span class="sxs-lookup"><span data-stu-id="b1768-194">Course catalog documents formatting and schema</span></span>

<span data-ttu-id="b1768-195">Документ должен быть в формате CSV с максимальным размером 18 МБ.</span><span class="sxs-lookup"><span data-stu-id="b1768-195">The document needs to be in CSV format with a maximum size of 18 MB.</span></span> <span data-ttu-id="b1768-196">Документ должен содержать обязательное название курса полей, его **ИД** и **URL-адрес курса.**</span><span class="sxs-lookup"><span data-stu-id="b1768-196">The document must contain the required fields **course title**, **course ID**, and **course URL**.</span></span> <span data-ttu-id="b1768-197">Включив рекомендуемые поля, вы повысите качество работы учащихся, возвращая более лучшие результаты поиска и определение навыков.</span><span class="sxs-lookup"><span data-stu-id="b1768-197">Including the recommended fields improves the experience for students by returning better search results and skill identification.</span></span>

> [!NOTE]
> <span data-ttu-id="b1768-198">Начните с [образца документа каталога]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) курса, чтобы приступить к работе.</span><span class="sxs-lookup"><span data-stu-id="b1768-198">Start with the [sample course catalog]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) document to get started.</span></span>

##### <a name="sample-csv-file"></a><span data-ttu-id="b1768-199">Пример .CSV файла</span><span class="sxs-lookup"><span data-stu-id="b1768-199">Sample .CSV file</span></span>

```
courseId,title,sourceLink,description,language,format,thumbnailLink,thumbnailAltText,educationLevel,topics
"AA-501","Analytics Foundations","https://example.com/course-id","This course equips the student with the knowledge and skills needed to conduct and present large-scale studies based on advanced analytics.","en-us","In-person","https://via.placeholder.com/360x200","Undergraduate","Alt text for the thumbnail","analytics, data science, data analysis, linear regression"
```

<span data-ttu-id="b1768-200">В следующей таблице показаны элементы, которые нужно включить в каталог курса:</span><span class="sxs-lookup"><span data-stu-id="b1768-200">The following table shows the items to include in the course catalog:</span></span>


| <span data-ttu-id="b1768-201">Имя</span><span class="sxs-lookup"><span data-stu-id="b1768-201">Name</span></span>             | <span data-ttu-id="b1768-202">Статус</span><span class="sxs-lookup"><span data-stu-id="b1768-202">Status</span></span>      | <span data-ttu-id="b1768-203">Тип</span><span class="sxs-lookup"><span data-stu-id="b1768-203">Type</span></span>   | <span data-ttu-id="b1768-204">Описание</span><span class="sxs-lookup"><span data-stu-id="b1768-204">Description</span></span>                                                                    |
|------------------|-------------|--------|--------------------------------------------------------------------------------|
| <span data-ttu-id="b1768-205">courseId</span><span class="sxs-lookup"><span data-stu-id="b1768-205">courseId</span></span>         | <span data-ttu-id="b1768-206">Обязательно</span><span class="sxs-lookup"><span data-stu-id="b1768-206">Required</span></span>    | <span data-ttu-id="b1768-207">Строка</span><span class="sxs-lookup"><span data-stu-id="b1768-207">string</span></span> | <span data-ttu-id="b1768-208">Как правило, это ид курса (обычно он сопописается с тем, что создается в записи разговоров).</span><span class="sxs-lookup"><span data-stu-id="b1768-208">Usually the course id (Typically maps to what is generated in the transcript).</span></span> |
| <span data-ttu-id="b1768-209">Название</span><span class="sxs-lookup"><span data-stu-id="b1768-209">title</span></span>            | <span data-ttu-id="b1768-210">Обязательно</span><span class="sxs-lookup"><span data-stu-id="b1768-210">Required</span></span>    | <span data-ttu-id="b1768-211">Строка</span><span class="sxs-lookup"><span data-stu-id="b1768-211">string</span></span> | <span data-ttu-id="b1768-212">Обычно название курса.</span><span class="sxs-lookup"><span data-stu-id="b1768-212">Usually the course title.</span></span>                                                      |
| <span data-ttu-id="b1768-213">sourceLink</span><span class="sxs-lookup"><span data-stu-id="b1768-213">sourceLink</span></span>       | <span data-ttu-id="b1768-214">Обязательно</span><span class="sxs-lookup"><span data-stu-id="b1768-214">Required</span></span>    | <span data-ttu-id="b1768-215">Url</span><span class="sxs-lookup"><span data-stu-id="b1768-215">URL</span></span>    | <span data-ttu-id="b1768-216">Ссылка веб-сайта на страницу курса.</span><span class="sxs-lookup"><span data-stu-id="b1768-216">Website link to the course page.</span></span>                                               |
| <span data-ttu-id="b1768-217">Описание</span><span class="sxs-lookup"><span data-stu-id="b1768-217">description</span></span>      | <span data-ttu-id="b1768-218">Рекомендуется</span><span class="sxs-lookup"><span data-stu-id="b1768-218">Recommended</span></span> | <span data-ttu-id="b1768-219">Строка</span><span class="sxs-lookup"><span data-stu-id="b1768-219">string</span></span> | <span data-ttu-id="b1768-220">Вводный текст курса.</span><span class="sxs-lookup"><span data-stu-id="b1768-220">Introduction text for the course.</span></span>                                              |
| <span data-ttu-id="b1768-221">Язык</span><span class="sxs-lookup"><span data-stu-id="b1768-221">language</span></span>         | <span data-ttu-id="b1768-222">Рекомендуется</span><span class="sxs-lookup"><span data-stu-id="b1768-222">Recommended</span></span> | <span data-ttu-id="b1768-223">Строка</span><span class="sxs-lookup"><span data-stu-id="b1768-223">string</span></span> | <span data-ttu-id="b1768-224">Язык курса.</span><span class="sxs-lookup"><span data-stu-id="b1768-224">Language of the course.</span></span> <span data-ttu-id="b1768-225">Используйте стандартные языковые коды.</span><span class="sxs-lookup"><span data-stu-id="b1768-225">Use standard language codes.</span></span>                           |
| <span data-ttu-id="b1768-226">Формат</span><span class="sxs-lookup"><span data-stu-id="b1768-226">format</span></span>           | <span data-ttu-id="b1768-227">Рекомендуется</span><span class="sxs-lookup"><span data-stu-id="b1768-227">Recommended</span></span> | <span data-ttu-id="b1768-228">Строка</span><span class="sxs-lookup"><span data-stu-id="b1768-228">string</span></span> | <span data-ttu-id="b1768-229">Режим обучения, например, онлайн, видео, линлин.</span><span class="sxs-lookup"><span data-stu-id="b1768-229">Mode of teaching, e.g., online, video, in-person.</span></span>                              |
| <span data-ttu-id="b1768-230">thumbnailLink</span><span class="sxs-lookup"><span data-stu-id="b1768-230">thumbnailLink</span></span>    | <span data-ttu-id="b1768-231">Рекомендуется</span><span class="sxs-lookup"><span data-stu-id="b1768-231">Recommended</span></span> | <span data-ttu-id="b1768-232">Url</span><span class="sxs-lookup"><span data-stu-id="b1768-232">URL</span></span>    | <span data-ttu-id="b1768-233">Ссылка эскиза на изображение курса.</span><span class="sxs-lookup"><span data-stu-id="b1768-233">Thumbnail link to the course image.</span></span>                                            |
| <span data-ttu-id="b1768-234">thumbnailAltText</span><span class="sxs-lookup"><span data-stu-id="b1768-234">thumbnailAltText</span></span> | <span data-ttu-id="b1768-235">Рекомендуется</span><span class="sxs-lookup"><span data-stu-id="b1768-235">Recommended</span></span> | <span data-ttu-id="b1768-236">Строка</span><span class="sxs-lookup"><span data-stu-id="b1768-236">string</span></span> | <span data-ttu-id="b1768-237">Заме доступа к изображению</span><span class="sxs-lookup"><span data-stu-id="b1768-237">Accessibility alt text for the image</span></span>                                           |
| <span data-ttu-id="b1768-238">educationLevel</span><span class="sxs-lookup"><span data-stu-id="b1768-238">educationLevel</span></span>   | <span data-ttu-id="b1768-239">Рекомендуется</span><span class="sxs-lookup"><span data-stu-id="b1768-239">Recommended</span></span> | <span data-ttu-id="b1768-240">Строка</span><span class="sxs-lookup"><span data-stu-id="b1768-240">string</span></span> | <span data-ttu-id="b1768-241">Учебный уровень, пример.</span><span class="sxs-lookup"><span data-stu-id="b1768-241">Study level, ex.</span></span> <span data-ttu-id="b1768-242">Студент-выпускник.</span><span class="sxs-lookup"><span data-stu-id="b1768-242">Undergraduate/Graduate.</span></span>                                       |
| <span data-ttu-id="b1768-243">Темы</span><span class="sxs-lookup"><span data-stu-id="b1768-243">topics</span></span>           | <span data-ttu-id="b1768-244">Рекомендуется</span><span class="sxs-lookup"><span data-stu-id="b1768-244">Recommended</span></span> | <span data-ttu-id="b1768-245">Строка</span><span class="sxs-lookup"><span data-stu-id="b1768-245">string</span></span> | <span data-ttu-id="b1768-246">Темы и теги, связанные с навыками, которые преподаются в курсах.</span><span class="sxs-lookup"><span data-stu-id="b1768-246">Topics or tags that are associated with the skills the courses teach.</span></span>          |

##### <a name="add-the-course-catalog"></a><span data-ttu-id="b1768-247">Добавление каталога курса</span><span class="sxs-lookup"><span data-stu-id="b1768-247">Add the course catalog</span></span>

1. <span data-ttu-id="b1768-248">Во sign in to the **Teams admin center**.</span><span class="sxs-lookup"><span data-stu-id="b1768-248">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="b1768-249">Выберите Teams **приложения** &gt; **Manage apps** Career &gt; **Coach** &gt; **Параметры** &gt; **course catalog**.  </span><span class="sxs-lookup"><span data-stu-id="b1768-249">Select **Teams apps** &gt; **Manage apps** &gt; **Career Coach** &gt; **Settings** &gt;  **Course catalog**.</span></span>

2. <span data-ttu-id="b1768-250">Upload курсы в формате CSV.</span><span class="sxs-lookup"><span data-stu-id="b1768-250">Upload courses in CSV format.</span></span>

4. <span data-ttu-id="b1768-251">Выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="b1768-251">Select **Apply**.</span></span>

   ![Раздел каталога курса приложения "Тренер по карьерной карьере"](media/course-catalog.png)

#### <a name="fields-of-study"></a><span data-ttu-id="b1768-253">Поля исследования</span><span class="sxs-lookup"><span data-stu-id="b1768-253">Fields of study</span></span>

<span data-ttu-id="b1768-254">Поля исследования являются синонимами с основными областями интересов, академическими и градусами.</span><span class="sxs-lookup"><span data-stu-id="b1768-254">The fields of study are synonymous with major areas of interest, academic major, and degree.</span></span> <span data-ttu-id="b1768-255">На эти названия ссылается студент, когда он начинает использовать приложение и настраивает свой персонализированный профиль.</span><span class="sxs-lookup"><span data-stu-id="b1768-255">These titles are referenced by students when they start using the app and begin setting up their personalized profile.</span></span>

<span data-ttu-id="b1768-256">Добавьте все поля обучения, доступные учащимся, например инженерные, английский, бизнес и так далее.</span><span class="sxs-lookup"><span data-stu-id="b1768-256">Add all fields of study available to students such as Engineering, English, Business, and so on.</span></span> <span data-ttu-id="b1768-257">Список полей позволяет учащимся найти интересуют их поля и добавить в свой профиль область фокуса.</span><span class="sxs-lookup"><span data-stu-id="b1768-257">The list of fields lets students discover fields of study that may interest them and add their area of focus to their profile.</span></span>

> [!NOTE]
> <span data-ttu-id="b1768-258">Начните с [примера поля в документе.](https://aka.ms/career-coach/docs/it-admins/sample-fieldsofstudy)</span><span class="sxs-lookup"><span data-stu-id="b1768-258">Start with the [sample field of study](https://aka.ms/career-coach/docs/it-admins/sample-fieldsofstudy) document.</span></span>
##### <a name="add-the-fields-of-study"></a><span data-ttu-id="b1768-259">Добавление полей исследования</span><span class="sxs-lookup"><span data-stu-id="b1768-259">Add the fields of study</span></span>

1. <span data-ttu-id="b1768-260">Во sign in to the **Teams admin center**.</span><span class="sxs-lookup"><span data-stu-id="b1768-260">Sign in to the **Teams admin center**.</span></span>
1. <span data-ttu-id="b1768-261">Выберите **Teams приложения Manage** &gt; **apps** Career &gt; **Coach** &gt; **Параметры** Fields of Study &gt; (Поля **обучения).**  </span><span class="sxs-lookup"><span data-stu-id="b1768-261">Select **Teams apps** &gt; **Manage apps** &gt; **Career Coach** &gt; **Settings** &gt;  **Fields of study**.</span></span>

2. <span data-ttu-id="b1768-262">Upload в формате CSV.</span><span class="sxs-lookup"><span data-stu-id="b1768-262">Upload field of study in CSV format.</span></span>

3. <span data-ttu-id="b1768-263">Выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="b1768-263">Select **Apply**.</span></span>

#### <a name="customization"></a><span data-ttu-id="b1768-264">Настройки</span><span class="sxs-lookup"><span data-stu-id="b1768-264">Customization</span></span>

<span data-ttu-id="b1768-265">Тренера по карьерной карьере можно настроить так, чтобы он был уникальным для вашего учебного заведения.</span><span class="sxs-lookup"><span data-stu-id="b1768-265">Career Coach can be customized to be unique to your educational institution.</span></span> <span data-ttu-id="b1768-266">Настройка поддерживает добавление функций на панель мониторинга.</span><span class="sxs-lookup"><span data-stu-id="b1768-266">The customization supports adding experiences to the dashboard.</span></span> <span data-ttu-id="b1768-267">Рекомендуется добавлять ссылки на доски вакансий, мероприятия, офис служб по карьерной работе, мероприятия, связанные с карьерой, клубы учащихся и другие ресурсы, которые помогут учащимся получить реальный опыт.</span><span class="sxs-lookup"><span data-stu-id="b1768-267">It's recommended to add links to job boards, events, career services office, career-related events, student clubs, and any other resources that help students gain real-world experience.</span></span>

##### <a name="add-customized-experiences"></a><span data-ttu-id="b1768-268">Добавление настраиваемых функций</span><span class="sxs-lookup"><span data-stu-id="b1768-268">Add customized experiences</span></span>

1. <span data-ttu-id="b1768-269">Во sign in to the **Teams admin center**.</span><span class="sxs-lookup"><span data-stu-id="b1768-269">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="b1768-270">Выберите Teams **приложения Управление** &gt; **приложениями** &gt; **Coach для**  >  **Параметры** &gt; **настройки**.</span><span class="sxs-lookup"><span data-stu-id="b1768-270">Select **Teams apps** &gt; **Manage apps** &gt; **Career Coach** > **Settings** &gt; **Customization**.</span></span>

2. <span data-ttu-id="b1768-271">Добавьте каждый URL-адрес, заголовок и краткое описание.</span><span class="sxs-lookup"><span data-stu-id="b1768-271">Add each URL, a title, and short description.</span></span>  
  
3. <span data-ttu-id="b1768-272">Выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="b1768-272">Select **Apply**.</span></span>

### <a name="enable-the-app"></a><span data-ttu-id="b1768-273">Включить приложение</span><span class="sxs-lookup"><span data-stu-id="b1768-273">Enable the app</span></span>

<span data-ttu-id="b1768-274">После завершения настройки в включить приложение для учащихся и лицензированных пользователей, чтобы они могли получить доступ к тренеру по карьерной деятельности.</span><span class="sxs-lookup"><span data-stu-id="b1768-274">After you complete the configuration, enable the app for students and licensed users so they'll have access to Career Coach.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b1768-275">У вас должны быть разрешения глобального Teams роли администратора.</span><span class="sxs-lookup"><span data-stu-id="b1768-275">You must have Global or Teams admin role permissions.</span></span>

1. <span data-ttu-id="b1768-276">Во sign in to the **Teams admin center**.</span><span class="sxs-lookup"><span data-stu-id="b1768-276">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="b1768-277">Выберите Teams **приложения Manage** &gt; **apps** &gt; **Career Coach**.</span><span class="sxs-lookup"><span data-stu-id="b1768-277">Select **Teams apps** &gt; **Manage apps** &gt; **Career Coach**.</span></span>

2. <span data-ttu-id="b1768-278">Переместить в положение Разрешено положение состояние **.**</span><span class="sxs-lookup"><span data-stu-id="b1768-278">Move the Status toggle to **Allowed**.</span></span>  

  > [!NOTE]
  > <span data-ttu-id="b1768-279">Разрешено означает, что приложение доступно для пользователей в вашем образовательном учреждении.</span><span class="sxs-lookup"><span data-stu-id="b1768-279">Allowed means that the app is available for users in your educational institution.</span></span> <span data-ttu-id="b1768-280">Заблокировано означает, что приложение не доступно учащимся.</span><span class="sxs-lookup"><span data-stu-id="b1768-280">Blocked means that the app isn't available to students.</span></span>

#### <a name="pin-the-app"></a><span data-ttu-id="b1768-281">Закрепление приложения</span><span class="sxs-lookup"><span data-stu-id="b1768-281">Pin the app</span></span>

<span data-ttu-id="b1768-282">Закрепление тренера по карьерной деятельности сделает приложение более доступным и видимым для учащихся.</span><span class="sxs-lookup"><span data-stu-id="b1768-282">Pinning Career Coach will make the app more accessible and visible for students.</span></span>

1. <span data-ttu-id="b1768-283">Во sign in to the **Teams admin center**.</span><span class="sxs-lookup"><span data-stu-id="b1768-283">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="b1768-284">Выберите **Teams политики установки** &gt; **приложений** Ваша &gt; *политика*.</span><span class="sxs-lookup"><span data-stu-id="b1768-284">Select **Teams apps** &gt;**Setup policies** &gt; *Your policy*.</span></span> 

2. <span data-ttu-id="b1768-285">В **области Закрепленные приложения** выберите Добавить **приложения**.</span><span class="sxs-lookup"><span data-stu-id="b1768-285">Under **Pinned apps**, choose **Add apps**.</span></span>

1. <span data-ttu-id="b1768-286">Найщите **тренера по карьерной карьере,** а затем выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b1768-286">Search for **Career Coach**, and then select **Add**.</span></span>

1. <span data-ttu-id="b1768-287">Выберите порядок появления приложения и выберите **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b1768-287">Choose the order for the app to appear and select **Save**.</span></span>

   <span data-ttu-id="b1768-288">Учащиеся будут уведомлены в Microsoft Teams о том, что тренер по карьерной деятельности закреплен.</span><span class="sxs-lookup"><span data-stu-id="b1768-288">Students will be notified in Microsoft Teams that Career Coach has been pinned.</span></span>  

## <a name="resources"></a><span data-ttu-id="b1768-289">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="b1768-289">Resources</span></span>

<span data-ttu-id="b1768-290">Следующие ресурсы помогут вам спланировать приложение "Тренер по карьерной карьере".</span><span class="sxs-lookup"><span data-stu-id="b1768-290">The following resources will help you plan your Career Coach app.</span></span>

- [<span data-ttu-id="b1768-291">Знакомство с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b1768-291">Welcome to Microsoft Teams</span></span>](Teams-overview.md)

- [<span data-ttu-id="b1768-292">Как выполнить развертывание Teams</span><span class="sxs-lookup"><span data-stu-id="b1768-292">How to roll out Teams</span></span>](get-started-with-teams-resources-for-org-wide-rollout.md?tabs=SmallBusiness)

- [<span data-ttu-id="b1768-293">Обзор команд и каналов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b1768-293">Overview of teams and channels in Microsoft Teams</span></span>](teams-channels-overview.md)

- [<span data-ttu-id="b1768-294">Управление приложениями в Microsoft Teams администрирования</span><span class="sxs-lookup"><span data-stu-id="b1768-294">Managing apps in Microsoft Teams Admin Center</span></span>](manage-apps.md)

- [<span data-ttu-id="b1768-295">Безопасность, конфиденциальность и соответствие требованиям в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b1768-295">Security, privacy, and compliance in Microsoft Teams</span></span>](security-compliance-overview.md)

- [<span data-ttu-id="b1768-296">Набор виртуальных ориентаций в Интернете</span><span class="sxs-lookup"><span data-stu-id="b1768-296">Online Virtual Orientation Kit</span></span>](https://www.microsoft.com/education/remote-learning/virtual-orientation) 

- [<span data-ttu-id="b1768-297">Ограничения и спецификация Teams каналов</span><span class="sxs-lookup"><span data-stu-id="b1768-297">Limits and specification of Teams channels</span></span>](limits-specifications-teams.md)

- [<span data-ttu-id="b1768-298">Расположение данных в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b1768-298">Location of data in Microsoft Teams</span></span>](location-of-data-in-teams.md)

- [<span data-ttu-id="b1768-299">Начало работы с обучением администраторов Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b1768-299">Getting started with admin training for Microsoft Teams</span></span>](ITAdmin-readiness.md)

- [<span data-ttu-id="b1768-300">Устранение неисправностей Teams</span><span class="sxs-lookup"><span data-stu-id="b1768-300">Teams troubleshooting</span></span>](/microsoftteams/troubleshoot/teams-welcome)

- [<span data-ttu-id="b1768-301">Управление политиками разрешений для приложений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b1768-301">Manage app permission policies in Microsoft Teams</span></span>](teams-app-permission-policies.md)
