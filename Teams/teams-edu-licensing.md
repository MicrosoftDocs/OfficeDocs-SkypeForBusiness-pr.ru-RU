---
title: Ресурсы Microsoft Teams для администраторов учебных заведений
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Пошаговое руководство по лицензированию для Microsoft Teams для учебных заведений.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b653acbe18d2247ccbf64a523fd237ca1415414
ms.sourcegitcommit: ac811017d54a55f39ecc0e3a66a883d9e027ce68
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "42547987"
---
# <a name="assign-microsoft-teams-licenses-for-edu"></a><span data-ttu-id="ae1f0-103">Назначение лицензий Microsoft Teams для учебных заведений</span><span class="sxs-lookup"><span data-stu-id="ae1f0-103">Assign Microsoft Teams licenses for EDU</span></span>

<span data-ttu-id="ae1f0-104">Microsoft Teams — это объединенное цифровое рабочее пространство для бесед, содержимого и приложений.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-104">Microsoft Teams is a digital hub that brings conversations, content, and apps together in one place.</span></span> <span data-ttu-id="ae1f0-105">Поскольку это пространство встроено в Office 365, интеграция с ним дает преимущества учебным заведениям, знакомым с приложениями и службами Office.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-105">Because it's built on Office 365, schools benefit from integration with their familiar Office apps and services.</span></span> <span data-ttu-id="ae1f0-106">Microsoft Teams может использоваться в вашем учебном заведении для того, чтобы создавать аудитории для совместной работы, объединяться в профессиональные образовательные сообщества и общаться с персоналом учебного заведения с помощью единого интерфейса в Office 365 для образовательных учреждений.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-106">Your institution can use Microsoft Teams to create collaborative classrooms, connect in professional learning communities, and communicate with school staff all from a single experience in Office 365 for Education.</span></span>

<span data-ttu-id="ae1f0-107">Чтобы начать работу, ИТ-администратору необходимо через центр администрирования Microsoft 365 [включить Microsoft Teams для вашего учебного заведения](https://docs.microsoft.com/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="ae1f0-107">To get started, IT administrators need to use the Microsoft 365 Admin Center to [enable Microsoft Teams for your school](https://docs.microsoft.com/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).</span></span>
<span data-ttu-id="ae1f0-108">После подключения необходимо назначить лицензии учетным записям пользователей, чтобы ваши преподаватели, сотрудники и учащиеся получили доступ к службам Office 365, в том числе Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-108">Once complete, you must assign licenses to user accounts so your faculty, staff, and students can access Office 365 services, such as Microsoft Teams.</span></span>

<span data-ttu-id="ae1f0-109">Назначать лицензии для учетных записей пользователей можно либо для каждой по отдельности, либо автоматически через членство в группах.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span> <span data-ttu-id="ae1f0-110">В этой статье приводится пошаговое описание процесса назначения лицензий Office 365 для отдельного пользователя или для небольшого числа учетных записей пользователей через Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-110">This article will walk you through how to assign Office 365 licenses to an individual or a small set of user accounts via the Microsoft 365 admin center.</span></span> <span data-ttu-id="ae1f0-111">О том, как назначать лицензии автоматически через членство в группах, можно узнать из указанных далее статей.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-111">To assign licenses automatically through group membership, see one of our supporting articles:</span></span>

- [<span data-ttu-id="ae1f0-112">Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae1f0-112">Office 365 Powershell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)
- [<span data-ttu-id="ae1f0-113">Назначение лицензий пользователям в соответствии с членством в группах в Active Directory</span><span class="sxs-lookup"><span data-stu-id="ae1f0-113">Group-based Licensing in Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)

<span data-ttu-id="ae1f0-114">Лицензии пользователям можно назначать на странице **Лицензии** или на странице **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-114">You can assign licenses to users on either the **Licenses** page, or on the **Active Users** page.</span></span> <span data-ttu-id="ae1f0-115">Выбор метода зависит от того, нужно ли назначить лицензии на продукты определенным пользователям или назначить пользователям лицензии на определенные продукты.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-115">Which method you use depends on whether you want to assign product licenses to specific users, or assign users licenses to specific products.</span></span>

> [!NOTE]
> <span data-ttu-id="ae1f0-116">Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования**, расположенного в верхней части главной страницы.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-116">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

## <a name="assign-licenses-to-users-on-the-licenses-page"></a><span data-ttu-id="ae1f0-117">Назначение лицензий пользователям на странице "Лицензии"</span><span class="sxs-lookup"><span data-stu-id="ae1f0-117">Assign licenses to users on the Licenses page</span></span>

> [!NOTE]
> <span data-ttu-id="ae1f0-118">Необходимо иметь права глобального администратора, администратора выставления счетов, администратора лицензий или администратора управления пользователями. Дополнительные сведения см. в статье [Роли администраторов в Office 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="ae1f0-118">You must be a Global admin, Billing admin, License admin, or User management admin. For more information, see [About Office 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="ae1f0-119">Через страницу **Лицензии** можно назначить лицензии на определенный продукт для не более чем 20 пользователей.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-119">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product for up to 20 users.</span></span> <span data-ttu-id="ae1f0-120">На странице **Лицензии** отображается список всех продуктов, на которые у вас есть подписки, а также общее количество лицензий для каждого продукта, количество назначенных и доступных лицензий.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-120">On the **Licenses** page, you see a list of all the products you have subscriptions for, together with the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

1. <span data-ttu-id="ae1f0-121">В Центре администрирования выберите **Выставление счетов** > на странице[Лицензии](https://go.microsoft.com/fwlink/p/?linkid=842264).</span><span class="sxs-lookup"><span data-stu-id="ae1f0-121">In the admin center, go to the **Billing** > [Licenses](https://go.microsoft.com/fwlink/p/?linkid=842264) page.</span></span>

   ![Снимок экрана с изображением окна для выставления счетов и пунктов меню.](media/EDU-Lic-Billing-License.png)
2. <span data-ttu-id="ae1f0-123">Выберите продукт, для которого нужно назначить лицензии.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-123">Select a product for which you want to assign licenses.</span></span> <span data-ttu-id="ae1f0-124">Microsoft Teams входит в бесплатную версию SKU Office 365 A1 для учащихся.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-124">Microsoft Teams is part of the free Office 365 A1 for Students SKU.</span></span>

   ![Снимок экрана с изображением страницы "Лицензии" с продуктами, лицензии на которые можно назначить.](media/EDU-Lic-Licenses-Products.png)
3. <span data-ttu-id="ae1f0-126">Нажмите **Назначение лицензий**.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-126">Select **Assign licenses**.</span></span>

   ![Снимок экрана с изображением раздела "Пользователи" на этой странице и пункта "Назначение лицензий" со значком "плюс" напротив него.](media/EDU-Lic-Assign-Licenses.png)
4. <span data-ttu-id="ae1f0-128">В панели **Назначение лицензий пользователям** начните вводить имя, благодаря чему отобразится список имен.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-128">In the **Assign licenses to users** pane, begin typing a name, which should generate a list of names.</span></span> <span data-ttu-id="ae1f0-129">Выберите среди результатов имя, которое вы ищете, и добавьте его к списку.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-129">Choose the name you're looking for from the results to add it to the list.</span></span> <span data-ttu-id="ae1f0-130">Вы можете добавить до 20 пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-130">You can add up to 20 users at a time.</span></span>

   ![Снимок экрана с изображением страницы "Назначение лицензий пользователям" с частично введенным именем и отображенными результатами поиска для этого частично введенного имени.](media/EDU-Lic-Assign-Licenses-Users.png)
5. <span data-ttu-id="ae1f0-132">Выберите **Включение и отключение приложений и служб**, чтобы назначить или удалить доступ к определенным элементам, например, к Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-132">Select **Turn apps and services on or off** to assign or remove access to specific items, such as Microsoft Teams.</span></span> <span data-ttu-id="ae1f0-133">Убедитесь в том, что выбраны **Microsoft Teams** и **Office в Интернете (для образовательных учреждений)**.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-133">Ensure **Microsoft Teams** and **Office for the web (Education)** are selected.</span></span>
6. <span data-ttu-id="ae1f0-134">После завершения нажмите **Назначить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-134">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="ae1f0-135">Изменение приложений и служб, к которым у пользователя есть доступ:</span><span class="sxs-lookup"><span data-stu-id="ae1f0-135">To change the apps and services a user has access to:</span></span>

1. <span data-ttu-id="ae1f0-136">Выберите строку с пользователем.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-136">Select the row that contains the user.</span></span>
1. <span data-ttu-id="ae1f0-137">В области справа выберите приложения и службы, к которым нужно предоставить доступ, или отмените выбор, чтобы удалить соответствующий доступ.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-137">In the right pane, select or deselect the apps and services that you want to give access to, or remove access from.</span></span>
1. <span data-ttu-id="ae1f0-138">После завершения нажмите **Сохранить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-138">When you're finished, select **Save**, then select **Close**.</span></span>

## <a name="assign-licenses-to-an-individual-or-multiple-users-on-the-active-users-page"></a><span data-ttu-id="ae1f0-139">Назначение лицензий одному или нескольким пользователям на странице "Активные пользователи"</span><span class="sxs-lookup"><span data-stu-id="ae1f0-139">Assign licenses to an individual or multiple users on the Active users page</span></span>

1. <span data-ttu-id="ae1f0-140">В Центре администрирования откройте страницу **Пользователи**  >  [Активные пользователи](https://go.microsoft.com/fwlink/p/?linkid=834822).</span><span class="sxs-lookup"><span data-stu-id="ae1f0-140">In the admin center, go to the **Users** > [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.</span></span>

   ![Снимок экрана с изображением пункта меню "Активные пользователи" в центре администрирования Microsoft O365.](media/EDU-Lic-Active-Users.png)
2. <span data-ttu-id="ae1f0-142">Установите флажки рядом с именем (именами) пользователя (пользователей), которому (которым) вы хотите назначить лицензии.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-142">Select the circles next to the name(s) of the user(s) you want to assign license(s) to.</span></span>

   ![Снимок экрана с изображением страницы "Активные пользователи" и списком активных пользователей на этой странице, часть из которых выбраны, так как заполнены кружки рядом с их именами.](media/EDU-Lic-Active-Users-List.png)
3. <span data-ttu-id="ae1f0-144">Нажмите вверху **Управление лицензиями на продукты**.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-144">At the top select **Manage product licenses**.</span></span>

   ![Снимок экрана с изображением вкладки "Управление лицензиями на продукты" и под ней — отображение пользователя с указанием на отсутствие у него лицензии.](media/EDU-Lic-Manage-Product-Licenses.png)
4. <span data-ttu-id="ae1f0-146">На панели **Управление лицензиями на продукты** выберите **Добавить к имеющимся назначениям лицензий на продукты** > **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-146">In the **Manage product licenses** pane, select **Add to existing product license assignments** > **Next**.</span></span>

   ![Снимок экрана с изображением окна "Управление лицензиями на продукты" с выбранным переключателем "Добавить к имеющимся назначениям лицензий на продукты".](media/EDU-Lic-Add-Existing-Product.png)
5. <span data-ttu-id="ae1f0-148">В области **Добавить к имеющимся продуктам** установите переключатель для лицензии, которую вы хотите назначить выбранным пользователям, в положение **Вкл.**.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-148">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span> <span data-ttu-id="ae1f0-149">Убедитесь в том, что выбраны **Microsoft Teams** и **Office в Интернете (для образовательных учреждений)**.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-149">Ensure **Microsoft Teams** and **Office for the web (Education)** are selected.</span></span>

   ![Снимок экрана с изображением Microsoft Teams и Office в Интернете (для образовательных учреждений), выбранных на вкладке "Добавить к имеющимся продуктам".](media/EDU-Lic-Add-Existing-Products.png)

   <span data-ttu-id="ae1f0-151">Пользователю (пользователям) по умолчанию автоматически назначаются все службы, связанные с этой лицензией (этими лицензиями).</span><span class="sxs-lookup"><span data-stu-id="ae1f0-151">By default, all services associated with those license(s) are automatically assigned to the user(s).</span></span> <span data-ttu-id="ae1f0-152">Вы можете ограничить доступные для пользователей службы.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-152">You can limit which services are available to the users.</span></span> <span data-ttu-id="ae1f0-153">Для служб, которых не должно быть у пользователей, установите переключатель в положение **Выкл**.</span><span class="sxs-lookup"><span data-stu-id="ae1f0-153">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="ae1f0-154">Внизу области выберите "Добавить" > "Закрыть".</span><span class="sxs-lookup"><span data-stu-id="ae1f0-154">At the bottom of the pane, select Add > Close.</span></span>
