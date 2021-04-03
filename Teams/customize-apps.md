---
title: Настройка приложений Майкрософт в Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: vaagarw
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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a87ce5f7dd63a78af4a7a1ea5f56aed1cad7263a
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574158"
---
# <a name="customize-apps-in-microsoft-teams"></a><span data-ttu-id="02df4-103">Настройка приложений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="02df4-103">Customize apps in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

 <span data-ttu-id="02df4-104">Microsoft Teams позволяет настраивать приложения для улучшения работы Teams.</span><span class="sxs-lookup"><span data-stu-id="02df4-104">Microsoft Teams provides app customization to enhance the Teams experience.</span></span> <span data-ttu-id="02df4-105">Некоторые разработчики приложений позволяют администратору Teams настраивать приложение. Администратор может изменить свойства приложения в зависимости от потребностей организации на  странице "Управление приложениями" Центра администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="02df4-105">Some app developers allow an app to be customized by the Teams admin. The admin can customize or rebrand the app properties based on the organizational needs using the Teams admin center **Manage apps** page.</span></span> <span data-ttu-id="02df4-106">Вы можете настроить такие сведения:</span><span class="sxs-lookup"><span data-stu-id="02df4-106">The details you can customize are:</span></span>

- <span data-ttu-id="02df4-107">Короткое имя</span><span class="sxs-lookup"><span data-stu-id="02df4-107">Short name</span></span>
- <span data-ttu-id="02df4-108">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="02df4-108">Short description</span></span>
- <span data-ttu-id="02df4-109">Полное описание</span><span class="sxs-lookup"><span data-stu-id="02df4-109">Full description</span></span>
- <span data-ttu-id="02df4-110">URL-адрес политики конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="02df4-110">Privacy policy URL</span></span>
- <span data-ttu-id="02df4-111">URL-адрес веб-сайта</span><span class="sxs-lookup"><span data-stu-id="02df4-111">Website URL</span></span>
- <span data-ttu-id="02df4-112">Условия использования URL-адреса</span><span class="sxs-lookup"><span data-stu-id="02df4-112">Terms of use URL</span></span>
- <span data-ttu-id="02df4-113">Значок цвета</span><span class="sxs-lookup"><span data-stu-id="02df4-113">Color icon</span></span>
- <span data-ttu-id="02df4-114">Значок "Контур"</span><span class="sxs-lookup"><span data-stu-id="02df4-114">Outline icon</span></span>
- <span data-ttu-id="02df4-115">Цвет акцента</span><span class="sxs-lookup"><span data-stu-id="02df4-115">Accent color</span></span>

<span data-ttu-id="02df4-116">Подробные [сведения о настраиваемых](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema) полях см. в схеме манифеста Teams.</span><span class="sxs-lookup"><span data-stu-id="02df4-116">See the [Teams Manifest schema](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema) for details about the fields that you can customize.</span></span>

## <a name="customize-the-apps-details"></a><span data-ttu-id="02df4-117">Настройка сведений о приложении</span><span class="sxs-lookup"><span data-stu-id="02df4-117">Customize the app's details</span></span>

<span data-ttu-id="02df4-118">Чтобы приступить к настройке приложения, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="02df4-118">To start customizing an app, complete the following steps:</span></span>

1. <span data-ttu-id="02df4-119">Войдите в Центр администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="02df4-119">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="02df4-120">Раз **развернуть приложения Teams** и выбрать **"Управление приложениями".**</span><span class="sxs-lookup"><span data-stu-id="02df4-120">Expand **Teams Apps** and select **Manage apps**.</span></span>
3. <span data-ttu-id="02df4-121">Проверьте **столбец "Настраиваемый"** в списке приложений и сортировать их по настраиваемым приложениям.</span><span class="sxs-lookup"><span data-stu-id="02df4-121">Check the **Customizable** column of the apps list and sort by apps that are customizable.</span></span>

   ![Отсорт настраиваемый столбец](media/customize-column.png)

   <span data-ttu-id="02df4-123">Для настройки можно получить доступ к трем точкам входа:</span><span class="sxs-lookup"><span data-stu-id="02df4-123">There are three entry points to access the customize feature:</span></span>

   - <span data-ttu-id="02df4-124">Выберите приложение, которое вы хотите настроить, а затем выберите **"Настроить".**</span><span class="sxs-lookup"><span data-stu-id="02df4-124">Select next to the app that you want to customize, and then select **Customize**.</span></span>

     ![Параметр "Настроить выбор" 1](media/select-app-to-customize1.png)

   - <span data-ttu-id="02df4-126">Выберите имя приложения, а затем его **можно настроить.**</span><span class="sxs-lookup"><span data-stu-id="02df4-126">Select the app name and then **Customizable**.</span></span>

     ![Параметр "Настроить выбор" 2](media/app-details-customizable.png)

   - <span data-ttu-id="02df4-128">Выберите имя приложения, а затем в  **выпадаке** "Действия" выберите "Настроить".</span><span class="sxs-lookup"><span data-stu-id="02df4-128">Select the app name, and then select **Customize** from the **Actions** dropdown.</span></span>

     ![Параметр "Настроить выбор" 3](media/customize-action-menu.png)

4. <span data-ttu-id="02df4-130">Раз развернуть **раздел "Сведения"** и настроить следующие поля:</span><span class="sxs-lookup"><span data-stu-id="02df4-130">Expand the **Details** section and customize the following fields:</span></span>

    - <span data-ttu-id="02df4-131">Короткое имя</span><span class="sxs-lookup"><span data-stu-id="02df4-131">Short name</span></span>
    - <span data-ttu-id="02df4-132">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="02df4-132">Short description</span></span>
    - <span data-ttu-id="02df4-133">Полное описание</span><span class="sxs-lookup"><span data-stu-id="02df4-133">Full description</span></span>
    - <span data-ttu-id="02df4-134">Веб-сайт</span><span class="sxs-lookup"><span data-stu-id="02df4-134">Website</span></span>
    - <span data-ttu-id="02df4-135">URL-адрес политики конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="02df4-135">Privacy policy URL</span></span>
    - <span data-ttu-id="02df4-136">Условия использования URL-адреса</span><span class="sxs-lookup"><span data-stu-id="02df4-136">Terms of use URL</span></span>

   ![Настройка параметров](media/customize-settings.png)

> [!Note]
> <span data-ttu-id="02df4-138">Будут видны только поля, которые разработчик приложения настроит.</span><span class="sxs-lookup"><span data-stu-id="02df4-138">Only the fields that the app developer has assigned as customizable will be visible.</span></span>

5. <span data-ttu-id="02df4-139">**Разорите раздел "Значок".**</span><span class="sxs-lookup"><span data-stu-id="02df4-139">Expand the **Icon** section.</span></span>

   <span data-ttu-id="02df4-140">а)</span><span class="sxs-lookup"><span data-stu-id="02df4-140">a.</span></span> <span data-ttu-id="02df4-141">Загрузите значок.</span><span class="sxs-lookup"><span data-stu-id="02df4-141">Upload an icon.</span></span> <span data-ttu-id="02df4-142">Используйте один полноцветный значок (192x192) пикселя в формате PNG.</span><span class="sxs-lookup"><span data-stu-id="02df4-142">Use one full-color icon (192x192) pixel in PNG format.</span></span>

   <span data-ttu-id="02df4-143">б)</span><span class="sxs-lookup"><span data-stu-id="02df4-143">b.</span></span> <span data-ttu-id="02df4-144">Выберите цвет контура значка.</span><span class="sxs-lookup"><span data-stu-id="02df4-144">Choose an icon outline color.</span></span> <span data-ttu-id="02df4-145">Используйте один прозрачный контур (32x32) пикселя в формате PNG.</span><span class="sxs-lookup"><span data-stu-id="02df4-145">Use one transparent outline (32x32) pixel in PNG format.</span></span>

   <span data-ttu-id="02df4-146">в.</span><span class="sxs-lookup"><span data-stu-id="02df4-146">c.</span></span> <span data-ttu-id="02df4-147">Выберите цвет акцента приложения, который соответствует значку.</span><span class="sxs-lookup"><span data-stu-id="02df4-147">Select an app accent color that matches the icon.</span></span>

    ![Настройка параметров цвета панели значков](media/customize-app-colors.png)

6. <span data-ttu-id="02df4-149">После настройки приложения выберите **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="02df4-149">Once your app has been customized, select **Apply**.</span></span>

7. <span data-ttu-id="02df4-150">Выберите **"Опубликовать",** чтобы опубликовать настроенную приложение.</span><span class="sxs-lookup"><span data-stu-id="02df4-150">Select **Publish** to publish the customized app.</span></span>

   <span data-ttu-id="02df4-151">Теперь настроенное приложение будет указано на странице **"Управление** приложениями".</span><span class="sxs-lookup"><span data-stu-id="02df4-151">The customized app is now listed in your **Manage apps** page.</span></span> <span data-ttu-id="02df4-152">У вас будет только одна версия приложения, так как при настройке функций приложения его копия не создается.</span><span class="sxs-lookup"><span data-stu-id="02df4-152">You'll have only one version of the app, since customizing the app features doesn't create a copy of the app.</span></span>

<span data-ttu-id="02df4-153">Теперь конечные пользователи Teams могут открыть клиент Teams, чтобы увидеть настроенную приложение.</span><span class="sxs-lookup"><span data-stu-id="02df4-153">Now your Teams end users can open their Teams client to see the customized app.</span></span>

   ![Настроено приложение в клиенте Teams](media/find-customized-app.png)

### <a name="special-considerations-for-customizing-an-app"></a><span data-ttu-id="02df4-155">Дополнительные факторы, которые следует учитывать при настройке приложения</span><span class="sxs-lookup"><span data-stu-id="02df4-155">Special considerations for customizing an app</span></span>

<span data-ttu-id="02df4-156">Следующая заметка содержит важные сведения о настройке приложения.</span><span class="sxs-lookup"><span data-stu-id="02df4-156">The following note includes important details about customizing an app.</span></span>

> [!Note]
> - <span data-ttu-id="02df4-157">При настройке приложений и любых описаниях, связанных с приложением, соблюдайте правила настройки, если они указаны издателем в документации или условиях использования приложения.</span><span class="sxs-lookup"><span data-stu-id="02df4-157">When you customize apps, and any description related to an app, ensure that you follow any customization guidelines if provided by the app publisher in their documentation or terms of use.</span></span> <span data-ttu-id="02df4-158">Вы также несете ответственность за соблюдение прав других лиц в отношении изображений сторонних организаций, которые вы можете использовать.</span><span class="sxs-lookup"><span data-stu-id="02df4-158">You're also responsible for respecting the rights of others regarding any third-party images you might use.</span></span>
> - <span data-ttu-id="02df4-159">Данные настройки, предоставленные администратором, хранятся в ближайшем регионе.</span><span class="sxs-lookup"><span data-stu-id="02df4-159">Admin-provided customization data is stored in the nearest region.</span></span>
> - <span data-ttu-id="02df4-160">Вы несете ответственность за обеспечение действительности ссылок на условия использования или политику конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="02df4-160">You are responsible for ensuring that links to terms of use or privacy policy are valid.</span></span>
> - <span data-ttu-id="02df4-161">Если издатель приложения больше не позволяет настраивать поля, на странице сведений о приложении появляется сообщение с уведомлением администратора о полях, которые невозможно изменить.</span><span class="sxs-lookup"><span data-stu-id="02df4-161">In case the app publisher no longer allows a field to be customizable, a message appears on the app details page notifying the admin about the fields that can't be customized any longer.</span></span> <span data-ttu-id="02df4-162">Все изменения, внесенные в поле, будут отменены с исходными значениями.</span><span class="sxs-lookup"><span data-stu-id="02df4-162">All the changes made to that field will be reverted to the original values.</span></span>
> - <span data-ttu-id="02df4-163">Для их изменения может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="02df4-163">Changes to branding might require up to 24 hours for the users to see the changes.</span></span>

## <a name="review-app-details"></a><span data-ttu-id="02df4-164">Просмотр сведений о приложении</span><span class="sxs-lookup"><span data-stu-id="02df4-164">Review app details</span></span>

<span data-ttu-id="02df4-165">Чтобы просмотреть сведения о приложении, вам может потребоваться просмотреть сведения о приложении.</span><span class="sxs-lookup"><span data-stu-id="02df4-165">You might want to see the app details to review the information.</span></span>

1. <span data-ttu-id="02df4-166">Войдите в Центр администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="02df4-166">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="02df4-167">Разверните раздел **Приложения Teams** и выберите **Управление приложениями**.</span><span class="sxs-lookup"><span data-stu-id="02df4-167">Expand **Teams apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="02df4-168">Выберите имя приложения.</span><span class="sxs-lookup"><span data-stu-id="02df4-168">Select the app name.</span></span>

4. <span data-ttu-id="02df4-169">Просмотр сведений о приложении, включая исходное имя приложения **Short name от издателя.**</span><span class="sxs-lookup"><span data-stu-id="02df4-169">View the app details, including the original app name **Short name from publisher**.</span></span>

   ![Настройка имени приложения на панели значков](media/app-details-original-name.png)

   <span data-ttu-id="02df4-171">Короткое **имя в поле publisher** отображается только в том случае, если вы изменили краткое имя приложения.</span><span class="sxs-lookup"><span data-stu-id="02df4-171">The **Short name from publisher** field is only visible if you've changed the app's short name.</span></span>

## <a name="reset-app-details-to-default"></a><span data-ttu-id="02df4-172">Сброс сведений о приложении до значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="02df4-172">Reset app details to default</span></span>

<span data-ttu-id="02df4-173">Вы можете в любое время восстановить исходные параметры сведений о приложении.</span><span class="sxs-lookup"><span data-stu-id="02df4-173">At any time, you can reset the app details to the original settings.</span></span>

1. <span data-ttu-id="02df4-174">Войдите в Центр администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="02df4-174">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="02df4-175">Раз **развернуть приложения Teams** и выбрать **"Управление приложениями".**</span><span class="sxs-lookup"><span data-stu-id="02df4-175">Expand **Teams Apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="02df4-176">Выберите имя приложения.</span><span class="sxs-lookup"><span data-stu-id="02df4-176">Select the app name.</span></span>

4. <span data-ttu-id="02df4-177">В **выпадании "Действия" выберите** **"Восстановить** по умолчанию".</span><span class="sxs-lookup"><span data-stu-id="02df4-177">Select **Reset to default** from the **Actions** dropdown.</span></span>

   ![Выделена кнопка "Восстановить по умолчанию"](media/select-reset.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="02df4-179">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="02df4-179">Frequently asked questions</span></span>

<span data-ttu-id="02df4-180">**Сколько времени займет мой пользователь, чтобы увидеть настроенную приложение?**</span><span class="sxs-lookup"><span data-stu-id="02df4-180">**How long will it take for my users to see the customized app?**</span></span>

<span data-ttu-id="02df4-181">Хотя администратор сразу же видит изменения в Центре администрирования Teams, на их просмотр пользователям может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="02df4-181">Although the admin can immediately see the changes in Teams Admin Center, it might take up to 24 hours for the end users to see the changes.</span></span>  

<span data-ttu-id="02df4-182">**Может ли поставщик приложения настроить приложение для своих клиентов?**</span><span class="sxs-lookup"><span data-stu-id="02df4-182">**Can the app provider customize the app for its customers?**</span></span>

 <span data-ttu-id="02df4-183">Нет, администратору клиента необходимо настроить приложение для своего клиента с помощью Центра администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="02df4-183">No, the admin of a tenant needs to customize the app for their tenant using the Teams Admin Center.</span></span>

<span data-ttu-id="02df4-184">**Будет ли настроенное приложение автоматически развернуто вместо текущего пользовательского приложения в клиенте?**</span><span class="sxs-lookup"><span data-stu-id="02df4-184">**Will the customized app automatically get deployed to replace my current custom app in a tenant?**</span></span>

<span data-ttu-id="02df4-185">Нет, администраторам клиентов придется вручную удалить все настраиваемые приложения и опубликовать его настроенную версию.</span><span class="sxs-lookup"><span data-stu-id="02df4-185">No, the tenant admins will have to manually remove any custom app and publish the customized version of the app.</span></span> <span data-ttu-id="02df4-186">Если вы настроили приложение и опубликовали его как пользовательское приложение, новое приложение, настроенное с помощью функции настройки приложения, не заменит текущее пользовательское приложение.</span><span class="sxs-lookup"><span data-stu-id="02df4-186">If you have customized an app and published it as a custom app, the new app customized using the app customization feature won't replace the current custom app.</span></span>  

<span data-ttu-id="02df4-187">**Будут ли в отчете об использовании приложений также демонстрироваться настроенные значения, такие как настроенное краткое имя?**</span><span class="sxs-lookup"><span data-stu-id="02df4-187">**Will the app usage report also show the customized values such as customized short name?**</span></span>

 <span data-ttu-id="02df4-188">Нет, в отчете об использовании приложений по-прежнему будет по-прежнему видно исходное имя приложения, отправленного от издателя.</span><span class="sxs-lookup"><span data-stu-id="02df4-188">No, the app usage report will still show the original name of the app sent from the publisher.</span></span>

<span data-ttu-id="02df4-189">**Какие приложения можно настраивать с помощью функции настройки приложений?**</span><span class="sxs-lookup"><span data-stu-id="02df4-189">**Which apps can I customize using the app customization feature?**</span></span>

<span data-ttu-id="02df4-190">Вы можете настраивать только приложения, которые разрешено настраивать издателем приложения.</span><span class="sxs-lookup"><span data-stu-id="02df4-190">You can only customize apps that have been allowed to be customizable by the app publisher.</span></span> <span data-ttu-id="02df4-191">Издателю приложения потребуется разрешить клиентам настраивать приложение.</span><span class="sxs-lookup"><span data-stu-id="02df4-191">The app publisher will need to opt in to allow its customers to customize the app.</span></span>

<span data-ttu-id="02df4-192">**Будут ли настроенные свойства показываться на экране разрешения graph?**</span><span class="sxs-lookup"><span data-stu-id="02df4-192">**Will the customized properties show up on the graph permission consent screen?**</span></span>

<span data-ttu-id="02df4-193">Нет, на экране согласия по-прежнему будет отслано исходное значение, отправленного издателем.</span><span class="sxs-lookup"><span data-stu-id="02df4-193">No, the permission consent screen will still show the original value sent by the publisher.</span></span>

## <a name="related-article"></a><span data-ttu-id="02df4-194">Связанная статья</span><span class="sxs-lookup"><span data-stu-id="02df4-194">Related article</span></span>

- [<span data-ttu-id="02df4-195">Управление приложениями</span><span class="sxs-lookup"><span data-stu-id="02df4-195">Manage apps</span></span>](manage-apps.md)
- [<span data-ttu-id="02df4-196">Настройка магазина приложений</span><span class="sxs-lookup"><span data-stu-id="02df4-196">Customize your app store</span></span>](customize-your-app-store.md)
