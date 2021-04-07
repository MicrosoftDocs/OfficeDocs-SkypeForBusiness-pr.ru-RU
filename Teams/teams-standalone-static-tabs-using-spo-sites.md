---
title: Создание приложения портала интрасети Teams с сайта или страницы SharePoint Online
author: cichur
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
description: Вы можете использовать существующий сайт или страницу SharePoint Online, а также создать отдельную персональную вкладку, которую можно использовать в своей организации в качестве портала интрасети.
localization_priority: Priority
ms.openlocfilehash: c6d138b1bf95edb619de6563f644e76ec123e3c6
ms.sourcegitcommit: 3861d661d32f507bd8479509ed09b1cfcf0b214f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2021
ms.locfileid: "51607547"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a><span data-ttu-id="952d1-103">Создание приложения портала интрасети Teams с сайта или страницы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="952d1-103">Create a Teams 'Intranet Portal app' from a SharePoint Online site or page</span></span>

<span data-ttu-id="952d1-104">Выполните действия, описанные в этой статье, чтобы создать отдельное статическое приложение в рамках Teams для связи с сайтом интрасети в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="952d1-104">Use the steps in this article to create a standalone and static app inside of Teams that links to the intranet site for your org.</span></span>

<span data-ttu-id="952d1-105">*Персональное приложение Teams* вашего сайта интрасети SharePoint создано и будет отображаться в виде вкладки в Teams.</span><span class="sxs-lookup"><span data-stu-id="952d1-105">A *Teams Personal App* of your SharePoint intranet site is created, and will appear as a tab inside of Teams.</span></span> <span data-ttu-id="952d1-106">На этой вкладке могут содержаться сведения, важные для всех ваших пользователей Teams.</span><span class="sxs-lookup"><span data-stu-id="952d1-106">This tab can contain information important to all your Teams users.</span></span> <span data-ttu-id="952d1-107">Это легкий и удобный способ доступа пользователей Teams к обновлениям всего одним щелчком мыши по вкладке.</span><span class="sxs-lookup"><span data-stu-id="952d1-107">It is a quick and convenient way for Teams users to access updates just a tab click away.</span></span>

<span data-ttu-id="952d1-108">Обратите внимание на то, что в продемонстрированном процессе для работы **необходимо использовать** *современный* сайт или страницу SharePoint.</span><span class="sxs-lookup"><span data-stu-id="952d1-108">Be aware that the process shown **must use** a *modern* SharePoint site or page to work.</span></span> <span data-ttu-id="952d1-109">Этот процесс недоступен для *классических* сайтов или страниц.</span><span class="sxs-lookup"><span data-stu-id="952d1-109">This process is not available for *classical* sites or pages.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="952d1-110">Убедитесь в том, что для вашего клиента включена загрузка приложений Teams.</span><span class="sxs-lookup"><span data-stu-id="952d1-110">Make certain that side-loading of Teams apps is enabled for your tenant.</span></span> <span data-ttu-id="952d1-111">В зависимости от того, в каком месте в процессе переноса портала администрирования Teams вы находитесь, может потребоваться включить его в разделе Teams > Администрирование, либо (в предыдущей версии портала) в разделе Администрирование > Службы и надстройки > Microsoft Teams > Приложения > Внешние приложения предыдущей версии портала.</span><span class="sxs-lookup"><span data-stu-id="952d1-111">Depending on where you are in the migration process of the Teams Admin portal, you might need to enable it either under Teams > Admin, or under Admin > Settings > Services and Add-ins > Microsoft Teams > Apps > External Apps, in the previous version of the portal!</span></span>

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a><span data-ttu-id="952d1-112">Создание отдельного приложения SharePoint Online с помощью App Studio</span><span class="sxs-lookup"><span data-stu-id="952d1-112">Use App Studio to create your standalone SharePoint Online app</span></span>

<span data-ttu-id="952d1-113">Подготовка.</span><span class="sxs-lookup"><span data-stu-id="952d1-113">Before you begin:</span></span>

1. <span data-ttu-id="952d1-114">Необходимо знать URL-адрес сайта или страницы современного обмена данными SharePoint Online или Team.</span><span class="sxs-lookup"><span data-stu-id="952d1-114">You'll need to know the URL of a SharePoint Online modern Communication or Team site, or page.</span></span>

   <span data-ttu-id="952d1-115">В путях к этим сайтам всегда будет присутствовать элемент */teams/* или */sites/*.</span><span class="sxs-lookup"><span data-stu-id="952d1-115">These sites will always have either */teams/* or */sites/* in their paths.</span></span>

2. <span data-ttu-id="952d1-116">Необходимо знать поддомен клиента, который будет использоваться в заполнителе **{{поддомен}}**.</span><span class="sxs-lookup"><span data-stu-id="952d1-116">You'll need to know your tenant's subdomain, which will be used in the placeholder **{{subdomain}}**.</span></span>

3. <span data-ttu-id="952d1-117">Эта статья будет использовать **{{siteUrl}}** в качестве заполнителя для *URL* выбранного вами сайта или страницы.</span><span class="sxs-lookup"><span data-stu-id="952d1-117">This article will use **{{siteUrl}}** as a placeholder for the *URL* of the site or page you chose.</span></span>

   <span data-ttu-id="952d1-118">Примеры *URL-адресов*:</span><span class="sxs-lookup"><span data-stu-id="952d1-118">Example *URLs*:</span></span>
   
   - `https://contoso.sharepoint.com/teams/Contoso`
      <br/><span data-ttu-id="952d1-119">*или*</span><span class="sxs-lookup"><span data-stu-id="952d1-119">*or*</span></span>
   - `https://contoso.sharepoint.com/sites/Contoso`
        
4. <span data-ttu-id="952d1-120">Кроме того, заполнитель **{{sitePath}}** будет использоваться для обозначения *пути* URL-адреса (например, /teams/Contoso).</span><span class="sxs-lookup"><span data-stu-id="952d1-120">Also, **{{sitePath}}** will be used to denote the *path* of the URL (ex: /teams/Contoso).</span></span>

   <span data-ttu-id="952d1-121">Примеры *путей*:</span><span class="sxs-lookup"><span data-stu-id="952d1-121">Example *paths*:</span></span>
   
   - <span data-ttu-id="952d1-122">/teams/Contoso</span><span class="sxs-lookup"><span data-stu-id="952d1-122">/teams/Contoso</span></span>
     <br/><span data-ttu-id="952d1-123">*или*</span><span class="sxs-lookup"><span data-stu-id="952d1-123">*or*</span></span>
   - <span data-ttu-id="952d1-124">/sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="952d1-124">/sites/Contoso</span></span>

<span data-ttu-id="952d1-125">Чтобы начать, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="952d1-125">Begin by following the steps below:</span></span>

1. <span data-ttu-id="952d1-126">Перейдите в магазин Teams.</span><span class="sxs-lookup"><span data-stu-id="952d1-126">Go to the Teams Store.</span></span>

2. <span data-ttu-id="952d1-127">Установите или откройте App Studio.</span><span class="sxs-lookup"><span data-stu-id="952d1-127">Install or open App Studio.</span></span>

3. <span data-ttu-id="952d1-128">Нажмите кнопку **Открыть**, расположенную рядом с пунктом "Приложение".</span><span class="sxs-lookup"><span data-stu-id="952d1-128">Click **Open**, next to the App option.</span></span>

4. <span data-ttu-id="952d1-129">В приложении App Studio выберите **Редактор манифестов**.</span><span class="sxs-lookup"><span data-stu-id="952d1-129">With App Studio open, click on **Manifest Editor**.</span></span>

5. <span data-ttu-id="952d1-130">**Создать новое приложение**.</span><span class="sxs-lookup"><span data-stu-id="952d1-130">**Create a new app**.</span></span>

6. <span data-ttu-id="952d1-131">Заполните все **Сведения о приложении**.</span><span class="sxs-lookup"><span data-stu-id="952d1-131">Fill in all **App Details**.</span></span>

7. <span data-ttu-id="952d1-132">Выберите пункт **Вкладки** в разделе "Возможности".</span><span class="sxs-lookup"><span data-stu-id="952d1-132">Click on **Tabs** under Capabilities.</span></span>

8. <span data-ttu-id="952d1-133">Нажмите кнопку **Добавить** вкладки "Личные данные".</span><span class="sxs-lookup"><span data-stu-id="952d1-133">Click **Add** under Personal Tab.</span></span>

9. <span data-ttu-id="952d1-134">Заполните поле **Имя** и выберите **новый уникальный идентификатор**.</span><span class="sxs-lookup"><span data-stu-id="952d1-134">Fill in the **Name** and choose **a new unique Entity ID**.</span></span>

10. <span data-ttu-id="952d1-135">Заполните поле **URL-адрес контента и URL-адрес веб-сайта**.</span><span class="sxs-lookup"><span data-stu-id="952d1-135">Fill in the **contentURL and Website URL**.</span></span>

    - <span data-ttu-id="952d1-136">**URL-адрес контента**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span><span class="sxs-lookup"><span data-stu-id="952d1-136">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span></span>  
    
    - <span data-ttu-id="952d1-137">**URL-адрес веб-сайта**: {{siteUrl}}</span><span class="sxs-lookup"><span data-stu-id="952d1-137">**websiteUrl**: {{siteUrl}}</span></span>

      <span data-ttu-id="952d1-138">Например, **URL-адрес контента**: </span><span class="sxs-lookup"><span data-stu-id="952d1-138">Example **contentURL**:</span></span>
      
      `https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub`

11. <span data-ttu-id="952d1-139">Перейдите в раздел **Домены и разрешения**.</span><span class="sxs-lookup"><span data-stu-id="952d1-139">Navigate to **Domains and Permissions**.</span></span> <span data-ttu-id="952d1-140">Убедитесь в том, что в разделе "Допустимые домены" указано ваше доменное имя SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="952d1-140">Make sure the valid domains section contains your SharePoint online domain name.</span></span>

    <span data-ttu-id="952d1-141">Пример: `contoso.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="952d1-141">Example: `contoso.sharepoint.com`</span></span>

12. <span data-ttu-id="952d1-142">Добавьте указанные ниже свойства **единого входа** веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="952d1-142">Add the following web app **single sign-on** properties:</span></span>

    <span data-ttu-id="952d1-143">Пример.</span><span class="sxs-lookup"><span data-stu-id="952d1-143">Example:</span></span>
    
    - <span data-ttu-id="952d1-144">**Идентификатор приложения AAD**: 00000003-0000-0ff1-ce00-000000000000</span><span class="sxs-lookup"><span data-stu-id="952d1-144">**AAD application ID**: 00000003-0000-0ff1-ce00-000000000000</span></span>
    
    - <span data-ttu-id="952d1-145">**Resource Url**: {{subdomain}}.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="952d1-145">**Resource Url**: {{subdomain}}.sharepoint.com</span></span>

      ![Единый вход в веб-приложение, с идентификатором и URL-адресом.](media/personal-app.png)

13. <span data-ttu-id="952d1-147">Выберите **Сохранить** эти свойства, а затем перейдите в раздел **Тестирование и распространение**.</span><span class="sxs-lookup"><span data-stu-id="952d1-147">**Save** these properties and then navigate to **Test and distribute**.</span></span>

14. <span data-ttu-id="952d1-148">Установите приложение, чтобы лично протестировать его.</span><span class="sxs-lookup"><span data-stu-id="952d1-148">Install the app to test the application personally.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="952d1-149">Если вы не используете приложение App Studio Teams, вам будет необходимо заархивировать в формате zip-созданный вами файл manifest.JSON, перейти в магазин приложений в Teams и нажать  **Отправка пользовательского приложения** по ссылке (в правом нижнем углу магазина приложений).</span><span class="sxs-lookup"><span data-stu-id="952d1-149">If you aren't using Teams App Studio, you will have to .zip the manifest.JSON file you just created, navigate to the App Store in Teams, and click  **upload custom app** link (at the bottom right of the App Store).</span></span> <span data-ttu-id="952d1-150">После этого приложение станет доступным для вас.</span><span class="sxs-lookup"><span data-stu-id="952d1-150">This will make the app available to you.</span></span>

15. <span data-ttu-id="952d1-151">Теперь приложение доступно в виде персональной вкладки, которую можно загружать и просматривать в Teams.</span><span class="sxs-lookup"><span data-stu-id="952d1-151">Now the app is available as a personal tab for you to load and view in Teams.</span></span>

## <a name="test-and-view-your-new-personal-tab"></a><span data-ttu-id="952d1-152">Проверка и просмотр новой персональной вкладки</span><span class="sxs-lookup"><span data-stu-id="952d1-152">Test and view your new personal tab</span></span>

<span data-ttu-id="952d1-153">Чтобы открыть вкладку на рабочем столе Teams, нажмите на многоточие (**...**) в левой части панели приложения.</span><span class="sxs-lookup"><span data-stu-id="952d1-153">To view the new tab on the Teams desktop, navigate to the ellipses (**…**) in the left-hand side of your app bar.</span></span> <span data-ttu-id="952d1-154">Найдите новое приложение, загрузите его и протестируйте ваше отдельное приложение в Teams.</span><span class="sxs-lookup"><span data-stu-id="952d1-154">Find your new app, load it, and test your standalone application in Teams.</span></span>

<span data-ttu-id="952d1-155">Если вы хотите, чтобы новое приложение было доступно в расположенном слева меню, то вам нужно воспользоваться параметром политики приложений.</span><span class="sxs-lookup"><span data-stu-id="952d1-155">If you want to make the new app available in the left menu at a higher position, you must use an app policy setting for this.</span></span> <span data-ttu-id="952d1-156">Этот параметр можно найти в разделе Администрирование Teams > Политики приложений > Добавление закрепленного приложения.</span><span class="sxs-lookup"><span data-stu-id="952d1-156">This setting can be found under the Team admin section > app policy > add a pinned application.</span></span> <span data-ttu-id="952d1-157">Когда вы назначаете политику пользователю для тестирования, изменение появится через несколько часов.</span><span class="sxs-lookup"><span data-stu-id="952d1-157">When you assign the policy to a user for testing, the change will appear a few hours later.</span></span> <span data-ttu-id="952d1-158">С учетом этого определите, в каком месте удобнее всего показывать приложение, чтобы избежать задержек.</span><span class="sxs-lookup"><span data-stu-id="952d1-158">With this in mind, please decide where the app should appear at your earliest convenience to help avoid delays.</span></span>

<span data-ttu-id="952d1-159">Чтобы просмотреть и протестировать новое приложение на мобильном устройстве, откройте ящик приложений, нажав значок в виде шеврона (**^**) над панелью вкладок в нижней части экрана.</span><span class="sxs-lookup"><span data-stu-id="952d1-159">To view and test the new app on a mobile device, open the app drawer by tapping on the chevron (**^**) above the tab bar near the bottom of your screen.</span></span> <span data-ttu-id="952d1-160">Найдите приложение и откройте его на своем мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="952d1-160">Find your app and navigate to it on your mobile device.</span></span>

## <a name="a-sample-manifestjson-file"></a><span data-ttu-id="952d1-161">Пример файла manifest.JSON.</span><span class="sxs-lookup"><span data-stu-id="952d1-161">A Sample Manifest.JSON file</span></span>

<span data-ttu-id="952d1-162">Созданный вами файл JSON будет выглядеть примерно так, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="952d1-162">The JSON file you generate will look something like the one below.</span></span>

```json
{

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.9/MicrosoftTeams.schema.json",

    "manifestVersion": "1.9",

    "version": "1.0.0",

    "id": "33ebded3-931c-4333-b0c5-b51dd8738873",

    "packageName": "com.contoso.teams.devapp",

    "developer": {

        "name": "Contoso",

        "websiteUrl": "https://www.contoso.com",

        "privacyUrl": "https://www.contoso.com/privacy",

        "termsOfUseUrl": "https://www.contoso.com/terms"

    },

    "icons": {

        "color": "color.png",

        "outline": "outline.png"

    },

    "name": {

        "short": "Contoso Intranet",

        "full": "Intranet Portal for Contoso"

    },

    "description": {

        "short": "Intranet portal for Contoso",

        "full": "This app is to demonstrate the capabilities of hosting a SharePoint communication and team site as a standalone app in Teams"

    },

    "accentColor": "#FFFFFF",

    "staticTabs": [

        {

            "entityId": "communicationSiteTab",

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
