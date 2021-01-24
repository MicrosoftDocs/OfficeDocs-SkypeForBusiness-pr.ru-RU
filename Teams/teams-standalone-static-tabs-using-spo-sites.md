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
ms.openlocfilehash: 7989478bf7fb81abdbd6ad9e553845302953c8cd
ms.sourcegitcommit: 5473b9fcd2bfe8adeb05a4a8d23e4350c7970fb6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49937511"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a>Создание приложения портала интрасети Teams с сайта или страницы SharePoint Online

Выполните действия, описанные в этой статье, чтобы создать отдельное статическое приложение в рамках Teams для связи с сайтом интрасети в вашей организации.

*Персональное приложение Teams* вашего сайта интрасети SharePoint создано и будет отображаться в виде вкладки в Teams. На этой вкладке могут содержаться сведения, важные для всех ваших пользователей Teams. Это легкий и удобный способ доступа пользователей Teams к обновлениям всего одним щелчком мыши по вкладке.

Обратите внимание на то, что в продемонстрированном процессе для работы **необходимо использовать** *современный* сайт или страницу SharePoint. Этот процесс недоступен для *классических* сайтов или страниц.

> [!IMPORTANT]
> Убедитесь в том, что для вашего клиента включена загрузка приложений Teams. В зависимости от того, в каком месте в процессе переноса портала администрирования Teams вы находитесь, может потребоваться включить его в разделе Teams > Администрирование, либо (в предыдущей версии портала) в разделе Администрирование > Службы и надстройки > Microsoft Teams > Приложения > Внешние приложения предыдущей версии портала.

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a>Создание отдельного приложения SharePoint Online с помощью App Studio

Подготовка.

1. Необходимо знать URL-адрес сайта или страницы современного обмена данными SharePoint Online или Team.

   В путях к этим сайтам всегда будет присутствовать элемент */teams/* или */sites/*.

2. Необходимо знать поддомен клиента, который будет использоваться в заполнителе **{{поддомен}}**.

3. Эта статья будет использовать **{{siteUrl}}** в качестве заполнителя для *URL* выбранного вами сайта или страницы.

   Примеры *URL-адресов*:
   
   - `https://contoso.sharepoint.com/teams/Contoso`
      <br/>*или*
   - `https://contoso.sharepoint.com/sites/Contoso`
        
4. Кроме того, заполнитель **{{sitePath}}** будет использоваться для обозначения *пути* URL-адреса (например, /teams/Contoso).

   Примеры *путей*:
   
   - /teams/Contoso
     <br/>*или*
   - /sites/Contoso

Чтобы начать, выполните указанные ниже действия.

1. Перейдите в магазин Teams.

2. Установите или откройте App Studio.

3. Нажмите кнопку **Открыть**, расположенную рядом с пунктом "Приложение".

4. В приложении App Studio выберите **Редактор манифестов**.

5. **Создать новое приложение**.

6. Заполните все **Сведения о приложении**.

7. Выберите пункт **Вкладки** в разделе "Возможности".

8. Нажмите кнопку **Добавить** вкладки "Личные данные".

9. Заполните поле **Имя** и выберите **новый уникальный идентификатор**.

10. Заполните поле **URL-адрес контента и URL-адрес веб-сайта**.

    - **URL-адрес контента**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}  
    
    - **URL-адрес веб-сайта**: {{siteUrl}}

      Например, **URL-адрес контента**: 
      
      `https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub`

11. Перейдите в раздел **Домены и разрешения**. Убедитесь в том, что в разделе "Допустимые домены" указано ваше доменное имя SharePoint Online.

    Пример: `contoso.sharepoint.com`

12. Добавьте указанные ниже свойства **единого входа** веб-приложения.

    Пример.
    
    - **Идентификатор приложения AAD**: 00000003-0000-0ff1-ce00-000000000000
    
    - **Resource Url**: {{subdomain}}.sharepoint.com

      ![Единый вход в веб-приложение, с идентификатором и URL-адресом.](media/personal-app.png)

13. Выберите **Сохранить** эти свойства, а затем перейдите в раздел **Тестирование и распространение**.

14. Установите приложение, чтобы лично протестировать его.

    > [!IMPORTANT]
    > Если вы не используете приложение App Studio Teams, вам будет необходимо заархивировать в формате zip-созданный вами файл manifest.JSON, перейти в магазин приложений в Teams и нажать  **Отправка пользовательского приложения** по ссылке (в правом нижнем углу магазина приложений). После этого приложение станет доступным для вас.

15. Теперь приложение доступно в виде персональной вкладки, которую можно загружать и просматривать в Teams.

## <a name="test-and-view-your-new-personal-tab"></a>Проверка и просмотр новой персональной вкладки

Чтобы открыть вкладку на рабочем столе Teams, нажмите на многоточие (**...**) в левой части панели приложения. Найдите новое приложение, загрузите его и протестируйте ваше отдельное приложение в Teams.

Если вы хотите, чтобы новое приложение было доступно в расположенном слева меню, то вам нужно воспользоваться параметром политики приложений. Этот параметр можно найти в разделе Администрирование Teams > Политики приложений > Добавление закрепленного приложения. Когда вы назначаете политику пользователю для тестирования, изменение появится через несколько часов. С учетом этого определите, в каком месте удобнее всего показывать приложение, чтобы избежать задержек.

Чтобы просмотреть и протестировать новое приложение на мобильном устройстве, откройте ящик приложений, нажав значок в виде шеврона (**^**) над панелью вкладок в нижней части экрана. Найдите приложение и откройте его на своем мобильном устройстве.

## <a name="a-sample-manifestjson-file"></a>Пример файла manifest.JSON.

Созданный вами файл JSON будет выглядеть примерно так, как показано ниже.

```json
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
