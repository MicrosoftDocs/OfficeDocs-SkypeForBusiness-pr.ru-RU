---
title: Настройка приложений Майкрософт в Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Узнайте, как настроить приложения в Microsoft Teams.
ms.openlocfilehash: 100a01c541c79ab62f10f3e11f086cdef5a11996
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059183"
---
# <a name="customize-apps-in-microsoft-teams"></a><span data-ttu-id="239b2-103">Настройка приложений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="239b2-103">Customize apps in Microsoft Teams</span></span>

 <span data-ttu-id="239b2-104">Microsoft Teams позволяет настраивать приложения для улучшения работы Teams.</span><span class="sxs-lookup"><span data-stu-id="239b2-104">Microsoft Teams provides app customization to enhance the Teams experience.</span></span> <span data-ttu-id="239b2-105">Некоторые разработчики приложений позволяют администратору Teams настраивать приложение. Администратор может изменить или изменить свойства приложения в зависимости от потребностей организации на странице Управление приложениями в Центре администрирования **Teams.**</span><span class="sxs-lookup"><span data-stu-id="239b2-105">Some app developers allow an app to be customized by the Teams admin. The admin can customize or rebrand the app properties based on the organizational needs using the Teams admin center **Manage apps** page.</span></span> <span data-ttu-id="239b2-106">Вы можете настроить такие сведения:</span><span class="sxs-lookup"><span data-stu-id="239b2-106">The details you can customize are:</span></span>

- <span data-ttu-id="239b2-107">Короткое имя</span><span class="sxs-lookup"><span data-stu-id="239b2-107">Short name</span></span>
- <span data-ttu-id="239b2-108">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="239b2-108">Short description</span></span>
- <span data-ttu-id="239b2-109">Полное описание</span><span class="sxs-lookup"><span data-stu-id="239b2-109">Full description</span></span>
- <span data-ttu-id="239b2-110">URL-адрес политики конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="239b2-110">Privacy policy URL</span></span>
- <span data-ttu-id="239b2-111">URL-адрес веб-сайта</span><span class="sxs-lookup"><span data-stu-id="239b2-111">Website URL</span></span>
- <span data-ttu-id="239b2-112">Условия использования URL-адреса</span><span class="sxs-lookup"><span data-stu-id="239b2-112">Terms of use URL</span></span>
- <span data-ttu-id="239b2-113">Значок цвета</span><span class="sxs-lookup"><span data-stu-id="239b2-113">Color icon</span></span>
- <span data-ttu-id="239b2-114">Значок "Контур"</span><span class="sxs-lookup"><span data-stu-id="239b2-114">Outline icon</span></span>
- <span data-ttu-id="239b2-115">Цвет акцента</span><span class="sxs-lookup"><span data-stu-id="239b2-115">Accent color</span></span>

<span data-ttu-id="239b2-116">Подробные [сведения о полях,](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema) которые можно настроить, см. в схеме манифеста Teams.</span><span class="sxs-lookup"><span data-stu-id="239b2-116">See the [Teams Manifest schema](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema) for details about the fields that you can customize.</span></span>

> [!NOTE]
> <span data-ttu-id="239b2-117">В настоящее время настройка приложений не поддерживается в GCCH или Отделе защиты (DoD).</span><span class="sxs-lookup"><span data-stu-id="239b2-117">Customizing apps isn't supported in Government Community Cloud High (GCCH) or Department of Defense (DoD) at this time.</span></span>

## <a name="customize-the-apps-details"></a><span data-ttu-id="239b2-118">Настройка сведений о приложении</span><span class="sxs-lookup"><span data-stu-id="239b2-118">Customize the app's details</span></span>

<span data-ttu-id="239b2-119">Чтобы начать настройку приложения, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="239b2-119">To start customizing an app, complete the following steps:</span></span>

1. <span data-ttu-id="239b2-120">Войдите в Центр администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="239b2-120">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="239b2-121">Раз **развернуть приложения Teams** и выбрать Управление **приложениями**.</span><span class="sxs-lookup"><span data-stu-id="239b2-121">Expand **Teams Apps** and select **Manage apps**.</span></span>
3. <span data-ttu-id="239b2-122">Проверьте **столбец Настраиваемый** список приложений и отсортировать их по настраиваемым приложениям.</span><span class="sxs-lookup"><span data-stu-id="239b2-122">Check the **Customizable** column of the apps list and sort by apps that are customizable.</span></span>

   ![Отсорт настраиваемый столбец](media/customize-column.png)

   <span data-ttu-id="239b2-124">Для доступа к функции настройки доступны три точки входа:</span><span class="sxs-lookup"><span data-stu-id="239b2-124">There are three entry points to access the customize feature:</span></span>

   - <span data-ttu-id="239b2-125">Выберите рядом с приложением, которое вы хотите настроить, и выберите **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="239b2-125">Select next to the app that you want to customize, and then select **Customize**.</span></span>

     ![Параметр настройки выделения 1](media/select-app-to-customize1.png)

   - <span data-ttu-id="239b2-127">Выберите имя приложения и выберите **настраиваемый .**</span><span class="sxs-lookup"><span data-stu-id="239b2-127">Select the app name and then **Customizable**.</span></span>

     ![Параметр настройки выделения 2](media/app-details-customizable.png)

   - <span data-ttu-id="239b2-129">Выберите имя приложения, а затем в **dropdown Actions (Действия)** выберите **настроить.**</span><span class="sxs-lookup"><span data-stu-id="239b2-129">Select the app name, and then select **Customize** from the **Actions** dropdown.</span></span>

     ![Параметр настройки выделения 3](media/customize-action-menu.png)

4. <span data-ttu-id="239b2-131">**Разорите раздел** Сведения и настройте следующие поля:</span><span class="sxs-lookup"><span data-stu-id="239b2-131">Expand the **Details** section and customize the following fields:</span></span>

    - <span data-ttu-id="239b2-132">Короткое имя</span><span class="sxs-lookup"><span data-stu-id="239b2-132">Short name</span></span>
    - <span data-ttu-id="239b2-133">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="239b2-133">Short description</span></span>
    - <span data-ttu-id="239b2-134">Полное описание</span><span class="sxs-lookup"><span data-stu-id="239b2-134">Full description</span></span>
    - <span data-ttu-id="239b2-135">Сайт</span><span class="sxs-lookup"><span data-stu-id="239b2-135">Website</span></span>
    - <span data-ttu-id="239b2-136">URL-адрес политики конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="239b2-136">Privacy policy URL</span></span>
    - <span data-ttu-id="239b2-137">Условия использования URL-адреса</span><span class="sxs-lookup"><span data-stu-id="239b2-137">Terms of use URL</span></span>

   ![Настройка параметров](media/customize-settings.png)

> [!Note]
> <span data-ttu-id="239b2-139">Будут видны только поля, которые разработчик приложения настроит.</span><span class="sxs-lookup"><span data-stu-id="239b2-139">Only the fields that the app developer has assigned as customizable will be visible.</span></span>

5. <span data-ttu-id="239b2-140">Разорите **раздел Значок.**</span><span class="sxs-lookup"><span data-stu-id="239b2-140">Expand the **Icon** section.</span></span>

   <span data-ttu-id="239b2-141">а)</span><span class="sxs-lookup"><span data-stu-id="239b2-141">a.</span></span> <span data-ttu-id="239b2-142">Добавить значок.</span><span class="sxs-lookup"><span data-stu-id="239b2-142">Upload an icon.</span></span> <span data-ttu-id="239b2-143">Используйте один полноцветный значок (192x192) в формате PNG.</span><span class="sxs-lookup"><span data-stu-id="239b2-143">Use one full-color icon (192x192) pixel in PNG format.</span></span>

   <span data-ttu-id="239b2-144">б)</span><span class="sxs-lookup"><span data-stu-id="239b2-144">b.</span></span> <span data-ttu-id="239b2-145">Выберите цвет контура значка.</span><span class="sxs-lookup"><span data-stu-id="239b2-145">Choose an icon outline color.</span></span> <span data-ttu-id="239b2-146">Используйте один прозрачный контур (32x32) пикселя в формате PNG.</span><span class="sxs-lookup"><span data-stu-id="239b2-146">Use one transparent outline (32x32) pixel in PNG format.</span></span>

   <span data-ttu-id="239b2-147">в.</span><span class="sxs-lookup"><span data-stu-id="239b2-147">c.</span></span> <span data-ttu-id="239b2-148">Выберите цвет со значком.</span><span class="sxs-lookup"><span data-stu-id="239b2-148">Select an app accent color that matches the icon.</span></span>

    ![Настройка параметров цвета панели значков](media/customize-app-colors.png)

6. <span data-ttu-id="239b2-150">После настройки приложения выберите Применить **.**</span><span class="sxs-lookup"><span data-stu-id="239b2-150">Once your app has been customized, select **Apply**.</span></span>

7. <span data-ttu-id="239b2-151">Чтобы **опубликовать настроенную** функцию, выберите опубликовать.</span><span class="sxs-lookup"><span data-stu-id="239b2-151">Select **Publish** to publish the customized app.</span></span>

   <span data-ttu-id="239b2-152">Теперь настроенное приложение будет указано на странице **Управление приложениями.**</span><span class="sxs-lookup"><span data-stu-id="239b2-152">The customized app is now listed in your **Manage apps** page.</span></span> <span data-ttu-id="239b2-153">У вас будет только одна версия приложения, так как при настройке функций приложения его копия не создается.</span><span class="sxs-lookup"><span data-stu-id="239b2-153">You'll have only one version of the app, since customizing the app features doesn't create a copy of the app.</span></span>

<span data-ttu-id="239b2-154">Теперь конечные пользователи Teams могут открыть клиент Teams, чтобы увидеть настроенную приложение.</span><span class="sxs-lookup"><span data-stu-id="239b2-154">Now your Teams end users can open their Teams client to see the customized app.</span></span>

   ![Настроено приложение в клиенте Teams](media/contoso-app.png)

### <a name="special-considerations-for-customizing-an-app"></a><span data-ttu-id="239b2-156">Особые моменты для настройки приложения</span><span class="sxs-lookup"><span data-stu-id="239b2-156">Special considerations for customizing an app</span></span>

<span data-ttu-id="239b2-157">В следующей заметке содержатся важные сведения о настройке приложения.</span><span class="sxs-lookup"><span data-stu-id="239b2-157">The following note includes important details about customizing an app.</span></span>

> [!Note]
> - <span data-ttu-id="239b2-158">При настройке приложений и любых описаний, связанных с приложением, убедитесь, что вы придерживались каких-либо рекомендаций по настройке, если издатель приложения предоставляет их документацию или условия использования.</span><span class="sxs-lookup"><span data-stu-id="239b2-158">When you customize apps, and any description related to an app, ensure that you follow any customization guidelines if provided by the app publisher in their documentation or terms of use.</span></span> <span data-ttu-id="239b2-159">Кроме того, вы несете ответственность за соблюдение прав других людей в отношении изображений сторонних сторон, которые вы можете использовать.</span><span class="sxs-lookup"><span data-stu-id="239b2-159">You're also responsible for respecting the rights of others regarding any third-party images you might use.</span></span>
> - <span data-ttu-id="239b2-160">Данные настройки, предоставленные администратором, хранятся в ближайшем регионе.</span><span class="sxs-lookup"><span data-stu-id="239b2-160">Admin-provided customization data is stored in the nearest region.</span></span>
> - <span data-ttu-id="239b2-161">Вы несете ответственность за то, чтобы ссылки на условия использования или политику конфиденциальности были допустимы.</span><span class="sxs-lookup"><span data-stu-id="239b2-161">You are responsible for ensuring that links to terms of use or privacy policy are valid.</span></span>
> - <span data-ttu-id="239b2-162">Если издатель приложения больше не разрешает настраивать поле, на странице сведений о приложении появится сообщение с уведомлением администратора о полях, которые больше нельзя настроить.</span><span class="sxs-lookup"><span data-stu-id="239b2-162">In case the app publisher no longer allows a field to be customizable, a message appears on the app details page notifying the admin about the fields that can't be customized any longer.</span></span> <span data-ttu-id="239b2-163">Все изменения, внесенные в это поле, будут отменены с исходными значениями.</span><span class="sxs-lookup"><span data-stu-id="239b2-163">All the changes made to that field will be reverted to the original values.</span></span>
> - <span data-ttu-id="239b2-164">Для их изменения может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="239b2-164">Changes to branding might require up to 24 hours for the users to see the changes.</span></span>

## <a name="review-app-details"></a><span data-ttu-id="239b2-165">Просмотр сведений о приложении</span><span class="sxs-lookup"><span data-stu-id="239b2-165">Review app details</span></span>

<span data-ttu-id="239b2-166">Возможно, вы захотите просмотреть сведения о приложении, чтобы просмотреть их.</span><span class="sxs-lookup"><span data-stu-id="239b2-166">You might want to see the app details to review the information.</span></span>

1. <span data-ttu-id="239b2-167">Войдите в Центр администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="239b2-167">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="239b2-168">Разверните раздел **Приложения Teams** и выберите **Управление приложениями**.</span><span class="sxs-lookup"><span data-stu-id="239b2-168">Expand **Teams apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="239b2-169">Выберите имя приложения.</span><span class="sxs-lookup"><span data-stu-id="239b2-169">Select the app name.</span></span>

4. <span data-ttu-id="239b2-170">Просмотр сведений о приложении, включая исходное имя приложения **Краткое имя от издателя**.</span><span class="sxs-lookup"><span data-stu-id="239b2-170">View the app details, including the original app name **Short name from publisher**.</span></span>

   ![Настройка имени приложения панели значков](media/original-app-version.png)

   <span data-ttu-id="239b2-172">Поле **"Краткое имя** из publisher" отображается только в том случае, если вы изменили краткое имя приложения.</span><span class="sxs-lookup"><span data-stu-id="239b2-172">The **Short name from publisher** field is only visible if you've changed the app's short name.</span></span>

## <a name="reset-app-details-to-default"></a><span data-ttu-id="239b2-173">Сброс сведений о приложении по умолчанию</span><span class="sxs-lookup"><span data-stu-id="239b2-173">Reset app details to default</span></span>

<span data-ttu-id="239b2-174">Вы можете в любое время восстановить исходные параметры для сведений о приложении.</span><span class="sxs-lookup"><span data-stu-id="239b2-174">At any time, you can reset the app details to the original settings.</span></span>

1. <span data-ttu-id="239b2-175">Войдите в Центр администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="239b2-175">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="239b2-176">Раз **развернуть приложения Teams** и выбрать Управление **приложениями**.</span><span class="sxs-lookup"><span data-stu-id="239b2-176">Expand **Teams Apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="239b2-177">Выберите имя приложения.</span><span class="sxs-lookup"><span data-stu-id="239b2-177">Select the app name.</span></span>

4. <span data-ttu-id="239b2-178">В **dropdown Actions (Действия) выберите** **восстановить** значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="239b2-178">Select **Reset to default** from the **Actions** dropdown.</span></span>

   ![Выделена кнопка "Восстановить по умолчанию"](media/select-reset.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="239b2-180">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="239b2-180">Frequently asked questions</span></span>

<span data-ttu-id="239b2-181">**Сколько времени займет мой пользователь, чтобы увидеть настроенную настройку приложения?**</span><span class="sxs-lookup"><span data-stu-id="239b2-181">**How long will it take for my users to see the customized app?**</span></span>

<span data-ttu-id="239b2-182">Хотя администратор сразу же видит изменения в Центре администрирования Teams, пользователям может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="239b2-182">Although the admin can immediately see the changes in Teams Admin Center, it might take up to 24 hours for the end users to see the changes.</span></span>  

<span data-ttu-id="239b2-183">**Может ли поставщик приложения настроить приложение для своих клиентов?**</span><span class="sxs-lookup"><span data-stu-id="239b2-183">**Can the app provider customize the app for its customers?**</span></span>

 <span data-ttu-id="239b2-184">Нет, администратору клиента необходимо настроить приложение для своего клиента с помощью Центра администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="239b2-184">No, the admin of a tenant needs to customize the app for their tenant using the Teams Admin Center.</span></span>

<span data-ttu-id="239b2-185">**Будет ли настроенное приложение автоматически развернуто вместо текущего пользовательского приложения в клиенте?**</span><span class="sxs-lookup"><span data-stu-id="239b2-185">**Will the customized app automatically get deployed to replace my current custom app in a tenant?**</span></span>

<span data-ttu-id="239b2-186">Нет, администраторам клиентов придется вручную удалить все настраиваемые приложения и опубликовать его настроенную версию.</span><span class="sxs-lookup"><span data-stu-id="239b2-186">No, the tenant admins will have to manually remove any custom app and publish the customized version of the app.</span></span> <span data-ttu-id="239b2-187">Если вы настроили приложение и опубликовали его как пользовательское приложение, новое приложение, настроенное с помощью функции настройки приложения, не заменит текущее пользовательское приложение.</span><span class="sxs-lookup"><span data-stu-id="239b2-187">If you have customized an app and published it as a custom app, the new app customized using the app customization feature won't replace the current custom app.</span></span>  

<span data-ttu-id="239b2-188">**Будут ли в отчете об использовании приложений также демонстрироваться настроенные значения, такие как настроенное краткое имя?**</span><span class="sxs-lookup"><span data-stu-id="239b2-188">**Will the app usage report also show the customized values such as customized short name?**</span></span>

 <span data-ttu-id="239b2-189">Нет, в отчете об использовании приложений по-прежнему будет по-прежнему показываться исходное имя приложения, отправленного от издателя.</span><span class="sxs-lookup"><span data-stu-id="239b2-189">No, the app usage report will still show the original name of the app sent from the publisher.</span></span>

<span data-ttu-id="239b2-190">**Какие приложения можно настраивать с помощью функции настройки приложений?**</span><span class="sxs-lookup"><span data-stu-id="239b2-190">**Which apps can I customize using the app customization feature?**</span></span>

<span data-ttu-id="239b2-191">Настраивать можно только приложения, которые разрешено настраивать издателем.</span><span class="sxs-lookup"><span data-stu-id="239b2-191">You can only customize apps that have been allowed to be customizable by the app publisher.</span></span> <span data-ttu-id="239b2-192">Издателю приложения потребуется разрешить пользователям настраивать приложение.</span><span class="sxs-lookup"><span data-stu-id="239b2-192">The app publisher will need to opt in to allow its customers to customize the app.</span></span>

<span data-ttu-id="239b2-193">**Будут ли настроенные свойства показываться на экране согласия на разрешение графа?**</span><span class="sxs-lookup"><span data-stu-id="239b2-193">**Will the customized properties show up on the graph permission consent screen?**</span></span>

<span data-ttu-id="239b2-194">Нет, на экране согласия по-прежнему будет по-прежнему показываться исходное значение, отправленного издателем.</span><span class="sxs-lookup"><span data-stu-id="239b2-194">No, the permission consent screen will still show the original value sent by the publisher.</span></span>

## <a name="related-article"></a><span data-ttu-id="239b2-195">Связанная статья</span><span class="sxs-lookup"><span data-stu-id="239b2-195">Related article</span></span>

- [<span data-ttu-id="239b2-196">Управление приложениями</span><span class="sxs-lookup"><span data-stu-id="239b2-196">Manage apps</span></span>](manage-apps.md)
- [<span data-ttu-id="239b2-197">Настройка магазина приложений</span><span class="sxs-lookup"><span data-stu-id="239b2-197">Customize your app store</span></span>](customize-your-app-store.md)
