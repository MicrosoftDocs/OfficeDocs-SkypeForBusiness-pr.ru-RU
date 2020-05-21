---
title: Создание приложения портала интрасети Teams с сайта или страницы SharePoint Online
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
ms.reviewer: vinbel
search.appverid: MET150
description: Вы можете использовать существующий сайт или страницу SharePoint Online, а также создать отдельную статическую вкладку, которую можно использовать в вашей организации в качестве портала интрасети.
localization_priority: Priority
ms.openlocfilehash: 4777b744d76415f45718cb274f402556e1e28240
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326586"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a><span data-ttu-id="9618d-103">Создание приложения портала интрасети Teams с сайта или страницы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9618d-103">Create a Teams 'Intranet Portal app' from a SharePoint Online site or page</span></span>

<span data-ttu-id="9618d-104">Выполните действия, описанные в этой статье, чтобы создать отдельное статическое приложение в рамках Teams для связи с сайтом интрасети в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9618d-104">Use the steps in this article to create a standalone and static app inside of Teams that links to the intranet site for your org.</span></span>

<span data-ttu-id="9618d-105">*Персональное приложение Teams* вашего сайта интрасети SharePoint создано и будет отображаться в виде вкладки в Teams.</span><span class="sxs-lookup"><span data-stu-id="9618d-105">A *Teams Personal App* of your SharePoint intranet site is created, and will appear as a tab inside of Teams.</span></span> <span data-ttu-id="9618d-106">На этой вкладке могут содержаться сведения, важные для всех ваших пользователей Teams.</span><span class="sxs-lookup"><span data-stu-id="9618d-106">This tab can contain information important to all your Teams users.</span></span> <span data-ttu-id="9618d-107">Это легкий и удобный способ доступа пользователей Teams к обновлениям всего одним щелчком мыши по вкладке.</span><span class="sxs-lookup"><span data-stu-id="9618d-107">It is a quick and convenient way for Teams users to access updates just a tab click away.</span></span>

<span data-ttu-id="9618d-108">Обратите внимание на то, что в продемонстрированном процессе для работы **необходимо использовать** *современный* сайт или страницу SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9618d-108">Be aware that the process shown **must use** a *modern* SharePoint site or page to work.</span></span> <span data-ttu-id="9618d-109">Этот процесс недоступен для *классических* сайтов или страниц.</span><span class="sxs-lookup"><span data-stu-id="9618d-109">This process is not available for *classical* sites or pages.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9618d-110">Убедитесь в том, что для вашего клиента включена загрузка приложений Teams.</span><span class="sxs-lookup"><span data-stu-id="9618d-110">Make certain that side-loading of Teams apps is enabled for your tenant.</span></span> <span data-ttu-id="9618d-111">В зависимости от того, в каком месте в процессе переноса портала администрирования Teams вы находитесь, может потребоваться включить его в разделе Teams > Администрирование, либо (в предыдущей версии портала) в разделе Администрирование > Службы и надстройки > Microsoft Teams > Приложения > Внешние приложения предыдущей версии портала.</span><span class="sxs-lookup"><span data-stu-id="9618d-111">Depending on where you are in the migration process of the Teams Admin portal, you might need to enable it either under Teams > Admin, or under Admin > Settings > Services and Add-ins > Microsoft Teams > Apps > External Apps, in the previous version of the portal!</span></span>

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a><span data-ttu-id="9618d-112">Создание отдельного приложения SharePoint Online с помощью App Studio</span><span class="sxs-lookup"><span data-stu-id="9618d-112">Use App Studio to create your standalone SharePoint Online app</span></span>

<span data-ttu-id="9618d-113">Подготовка.</span><span class="sxs-lookup"><span data-stu-id="9618d-113">Before you begin:</span></span>

1. <span data-ttu-id="9618d-114">Необходимо знать URL-адрес сайта или страницы современного обмена данными SharePoint Online или Team.</span><span class="sxs-lookup"><span data-stu-id="9618d-114">You'll need to know the URL of a SharePoint Online modern Communication or Team site, or page.</span></span>
    - <span data-ttu-id="9618d-115">В путях к этим сайтам всегда будет присутствовать элемент */teams/* или */sites/*.</span><span class="sxs-lookup"><span data-stu-id="9618d-115">These sites will always have either */teams/* or */sites/* in their paths.</span></span>

2. <span data-ttu-id="9618d-116">Необходимо знать поддомен клиента, который будет использоваться в заполнителе **{{поддомен}}**.</span><span class="sxs-lookup"><span data-stu-id="9618d-116">You'll need to know your tenant's subdomain, which will be used in the placeholder **{{subdomain}}**.</span></span>

3. <span data-ttu-id="9618d-117">Эта статья будет использовать **{{siteUrl}}** в качестве заполнителя для *URL* выбранного вами сайта или страницы.</span><span class="sxs-lookup"><span data-stu-id="9618d-117">This article will use **{{siteUrl}}** as a placeholder for the *URL* of the site or page you chose.</span></span>
    - <span data-ttu-id="9618d-118">Например, *URL-адреса*:   https://contoso.sharepoint.com/teams/Contoso   *или* https://contoso.sharepoint.com/sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="9618d-118">Example *URLs*:   https://contoso.sharepoint.com/teams/Contoso   *or* https://contoso.sharepoint.com/sites/Contoso</span></span>
4. <span data-ttu-id="9618d-119">Кроме того, заполнитель **{{sitePath}}** будет использоваться для обозначения *пути* URL-адреса (например, /teams/Contoso).</span><span class="sxs-lookup"><span data-stu-id="9618d-119">Also, **{{sitePath}}** will be used to denote the *path* of the URL (ex: /teams/Contoso).</span></span>
    - <span data-ttu-id="9618d-120">Примеры *путей*:   /teams/Contoso   *или* /sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="9618d-120">Example *paths*:   /teams/Contoso   *or* /sites/Contoso</span></span>

<span data-ttu-id="9618d-121">Чтобы начать, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="9618d-121">Begin by following the steps below:</span></span>

1. <span data-ttu-id="9618d-122">Перейдите в магазин Teams.</span><span class="sxs-lookup"><span data-stu-id="9618d-122">Go to the Teams Store.</span></span>

2. <span data-ttu-id="9618d-123">Установите или откройте App Studio.</span><span class="sxs-lookup"><span data-stu-id="9618d-123">Install or open App Studio.</span></span>

3. <span data-ttu-id="9618d-124">Нажмите кнопку **Открыть**, расположенную рядом с пунктом "Приложение".</span><span class="sxs-lookup"><span data-stu-id="9618d-124">Click **Open**, next to the App option.</span></span>

4. <span data-ttu-id="9618d-125">В приложении App Studio выберите **Редактор манифестов**.</span><span class="sxs-lookup"><span data-stu-id="9618d-125">With App Studio open, click on **Manifest Editor**.</span></span>

5. <span data-ttu-id="9618d-126">**Создать новое приложение**.</span><span class="sxs-lookup"><span data-stu-id="9618d-126">**Create a new app**.</span></span>

6. <span data-ttu-id="9618d-127">Заполните все **Сведения о приложении**.</span><span class="sxs-lookup"><span data-stu-id="9618d-127">Fill in all **App Details**.</span></span>

7. <span data-ttu-id="9618d-128">Выберите пункт **Вкладки** в разделе "Возможности".</span><span class="sxs-lookup"><span data-stu-id="9618d-128">Click on **Tabs** under Capabilities.</span></span>

8. <span data-ttu-id="9618d-129">Нажмите кнопку **Добавить** вкладки "Личные данные".</span><span class="sxs-lookup"><span data-stu-id="9618d-129">Click **Add** under Personal Tab.</span></span>

9. <span data-ttu-id="9618d-130">Заполните поле **Имя** и выберите **новый уникальный идентификатор**.</span><span class="sxs-lookup"><span data-stu-id="9618d-130">Fill in the **Name** and choose **a new unique Entity ID**.</span></span>

10. <span data-ttu-id="9618d-131">Заполните поле **URL-адрес контента и URL-адрес веб-сайта**.</span><span class="sxs-lookup"><span data-stu-id="9618d-131">Fill in the **contentURL and Website URL**.</span></span>

- <span data-ttu-id="9618d-132">**URL-адрес контента**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span><span class="sxs-lookup"><span data-stu-id="9618d-132">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span></span>  
- <span data-ttu-id="9618d-133">**URL-адрес веб-сайта**: {{siteUrl}}</span><span class="sxs-lookup"><span data-stu-id="9618d-133">**websiteUrl**: {{siteUrl}}</span></span>

    <span data-ttu-id="9618d-134">Например, **URL-адрес контента**: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span><span class="sxs-lookup"><span data-stu-id="9618d-134">Example **contentURL**: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span></span>

11. <span data-ttu-id="9618d-135">Перейдите в раздел **Домены и разрешения**.</span><span class="sxs-lookup"><span data-stu-id="9618d-135">Navigate to **Domains and Permissions**.</span></span> <span data-ttu-id="9618d-136">Убедитесь в том, что в разделе "Допустимые домены" указано ваше доменное имя SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9618d-136">Make sure the valid domains section contains your SharePoint online domain name.</span></span>

    <span data-ttu-id="9618d-137">Например, contoso.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="9618d-137">Example: contoso.sharepoint.com</span></span>

12. <span data-ttu-id="9618d-138">Добавьте указанные ниже свойства **единого входа** веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="9618d-138">Add the following web app **single sign-on** properties:</span></span>

     <span data-ttu-id="9618d-139">Например,  **AAD application ID**: 00000003-0000-0ff1-ce00-000000000000  **Resource Url**: {{subdomain}}.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="9618d-139">Example:  **AAD application ID**: 00000003-0000-0ff1-ce00-000000000000  **Resource Url**: {{subdomain}}.sharepoint.com</span></span>

    ![Единый вход в веб-приложение, с идентификатором и URL-адресом.](media/personal-app.png)

13. <span data-ttu-id="9618d-141">Выберите **Сохранить** эти свойства, а затем перейдите в раздел **Тестирование и распространение**.</span><span class="sxs-lookup"><span data-stu-id="9618d-141">**Save** these properties and then navigate to **Test and distribute**.</span></span>

14. <span data-ttu-id="9618d-142">Установите приложение, чтобы лично протестировать его.</span><span class="sxs-lookup"><span data-stu-id="9618d-142">Install the app to test the application personally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9618d-143">Если вы не используете приложение App Studio Teams, вам будет необходимо заархивировать в формате zip-созданный вами файл manifest.JSON, перейти в магазин приложений в Teams и нажать  **Отправка пользовательского приложения** по ссылке (в правом нижнем углу магазина приложений).</span><span class="sxs-lookup"><span data-stu-id="9618d-143">If you aren't using Teams App Studio, you will have to .zip the manifest.JSON file you just created, navigate to the App Store in Teams, and click  **upload custom app** link (at the bottom right of the App Store).</span></span> <span data-ttu-id="9618d-144">После этого приложение станет доступным для вас.</span><span class="sxs-lookup"><span data-stu-id="9618d-144">This will make the app available to you.</span></span>

15. <span data-ttu-id="9618d-145">Теперь приложение доступно в виде статической вкладки, которую можно загружать и просматривать в Teams.</span><span class="sxs-lookup"><span data-stu-id="9618d-145">Now the app is available as a static tab for you to load and view in Teams.</span></span>

## <a name="test-and-view-your-new-static-tab"></a><span data-ttu-id="9618d-146">Проверка и просмотр новой статической вкладки</span><span class="sxs-lookup"><span data-stu-id="9618d-146">Test and view your new static tab</span></span>

<span data-ttu-id="9618d-147">Чтобы открыть вкладку на рабочем столе Teams, нажмите на многоточие (**...**) в левой части панели приложения.</span><span class="sxs-lookup"><span data-stu-id="9618d-147">To view the new tab on the Teams desktop, navigate to the ellipses (**…**) in the left-hand side of your app bar.</span></span> <span data-ttu-id="9618d-148">Найдите новое приложение, загрузите его и протестируйте ваше отдельное приложение в Teams.</span><span class="sxs-lookup"><span data-stu-id="9618d-148">Find your new app, load it, and test your standalone application in Teams.</span></span>

<span data-ttu-id="9618d-149">Если вы хотите, чтобы новое приложение было доступно в расположенном слева меню, то вам нужно воспользоваться параметром политики приложений.</span><span class="sxs-lookup"><span data-stu-id="9618d-149">If you want to make the new app available in the left menu at a higher position, you must use an app policy setting for this.</span></span> <span data-ttu-id="9618d-150">Этот параметр можно найти в разделе Администрирование Teams > Политики приложений > Добавление закрепленного приложения.</span><span class="sxs-lookup"><span data-stu-id="9618d-150">This setting can be found under the Team admin section > app policy > add a pinned application.</span></span> <span data-ttu-id="9618d-151">Когда вы назначаете политику пользователю для тестирования, изменение появится через несколько часов.</span><span class="sxs-lookup"><span data-stu-id="9618d-151">When you assign the policy to a user for testing, the change will appear a few hours later.</span></span> <span data-ttu-id="9618d-152">С учетом этого определите, в каком месте удобнее всего показывать приложение, чтобы избежать задержек.</span><span class="sxs-lookup"><span data-stu-id="9618d-152">With this in mind, please decide where the app should appear at your earliest convenience to help avoid delays.</span></span>

<span data-ttu-id="9618d-153">Чтобы просмотреть и протестировать новое приложение на мобильном устройстве, откройте ящик приложений, нажав значок в виде шеврона (**^**) над панелью вкладок в нижней части экрана.</span><span class="sxs-lookup"><span data-stu-id="9618d-153">To view and test the new app on a mobile device, open the app drawer by tapping on the chevron (**^**) above the tab bar near the bottom of your screen.</span></span> <span data-ttu-id="9618d-154">Найдите приложение и откройте его на своем мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="9618d-154">Find your app and navigate to it on your mobile device.</span></span>

> [!CAUTION]
> <span data-ttu-id="9618d-155">Поддержка мобильных приложений в настоящее время доступна в виде предварительного просмотра для разработчиков.</span><span class="sxs-lookup"><span data-stu-id="9618d-155">Mobile support is currently in Developer Preview.</span></span> <span data-ttu-id="9618d-156">Чтобы включить предварительный просмотр для разработчиков, перейдите к разделу Параметры > О программе и включите режим "Предварительный просмотр для разработчиков".</span><span class="sxs-lookup"><span data-stu-id="9618d-156">To enable Developer Preview, navigate to Settings > About and then enable Developer Preview mode.</span></span>

## <a name="a-sample-manifestjson-file"></a><span data-ttu-id="9618d-157">Пример файла manifest.JSON.</span><span class="sxs-lookup"><span data-stu-id="9618d-157">A Sample Manifest.JSON file</span></span>

<span data-ttu-id="9618d-158">Созданный вами файл JSO        будет выглядеть примерно так, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="9618d-158">The JSO        file you generate will look something like the one below.</span></span>

```JSON'
{

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.5/MicrosoftTeams.schema.json",

    "manifestVersion": "1.5",

    "version": "1.0.0",

    "id": "33ebded3-931c-4333-b0c5-b51dd8738873",

    "packageName": "com.contoso.teams.devapp",

    "developer": {

        "name": "Contoso", ''

        "websiteUrl": "https://www.contoso.com",

        "privacyUrl": "https://www.contoso.com/privacy",

        "termsOfUseUrl": "https://www.contoso.com/terms"

    },

    "icons": {

        "color": "color.png",

        "outline": "outline.png"

    },

    "name": {

        "short": "Contoso Intranet", '

        "full": "Intranet Portal for Contoso"

    },

    "des    ription": {

        "short": "Intranet portal for Contoso",

        "full": "This app is to demonstrate the capabilities of hosting a SharePoint communication and team site as a standalone app in Teams"

    },

    "accentColor": "#FFFFFF",

    "staticTabs": [

        {

                     "       nti        Id":       "com    unicat    onSi    eTab",

            "name": "Contoso Net",

            "contentUrl": "https://contoso.sharepoint.com/sites/ContosoNet/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoNet/",

            "websiteUrl": "https://contoso.sharepoint.com/sites/ContosoNet",

            "scopes": [

                "personal"

            ]

        },

        {

            "entityId": "teamSiteTab",

            "name": "Team Contoso",

            "contentUrl": "https://contoso.sharepoint.com/teams/TeamContoso/_layouts/15/teamslogon.aspx?SPFX=true&dest=/teams/TeamContoso/",

            "websiteUrl": "https://contoso.sharepoint.com/teams/TeamContoso",

            "scopes": [

                "personal"

            ]

        }

    ],

    "permissions": [

        "identity",

        "messageTeamMembers"

    ],

    "validDomains": [

        "contoso.sharepoint.com"

    ],

    "webApplicationInfo": {

        "id": "00000003-0000-0ff1-ce00-000000000000",

        "resource": "https://contoso.sharepoint.com"

    }

}
```
