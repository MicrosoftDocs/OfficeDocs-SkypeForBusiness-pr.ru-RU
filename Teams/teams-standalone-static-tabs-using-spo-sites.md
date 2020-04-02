---
title: Создание приложения "портал интрасети" для Рабочей группы на сайте SharePoint Online или на странице
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Вы можете использовать существующий сайт или страницу SharePoint Online и создать отдельную статическую вкладку, которая может использоваться в качестве портала интрасети для вашей организации.
localization_priority: Normal
ms.openlocfilehash: 772063a7444e9c31d2740ac48635dc0f2e367435
ms.sourcegitcommit: aaae9df142ebb844a1fea27d3ae3b95130903d6a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2020
ms.locfileid: "43100367"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a>Создание приложения "портал интрасети" для Рабочей группы на сайте SharePoint Online или на странице

Выполните действия, описанные в этой статье, чтобы создать автономное и статическое приложение в Teams, которое ссылается на сайт интрасети для вашей организации.

Будет создано *личное приложение Teams* вашего сайта SharePoint, и оно появится как вкладка в Teams. На этой вкладке могут содержаться сведения, важные для всех пользователей Teams. Это быстрый и удобный способ получить доступ к обновлениям только нажатием клавиши TAB для пользователей Teams.

Имейте в виду, что процесс, показанный для работы, **должен использовать** *современный* сайт или страницу SharePoint. Этот процесс недоступен для *классических* сайтов и страниц.

> [!IMPORTANT]
> Убедитесь в том, что для вашего клиента включена параллельная загрузка приложений Teams. В зависимости от того, где находится миграция на портале администрирования Teams, вам может потребоваться включить ее в разделе администратор Teams > или в разделе Параметры администрирования > > службы и надстройки > Microsoft Teams > приложения > внешние приложения в предыдущей версии портала. 

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a>Создание автономного приложения SharePoint Online с помощью App Studio

Прежде чем начать, выполните указанные ниже действия.
1. Вам необходимо знать URL-адрес SharePoint Online с современной связью или сайт группы или страницу.
    - Эти сайты всегда будут содержать */Teams/* или */Sites/* в пути.

2. Вам необходимо знать поддомен клиента, который будет использоваться в заполнителе **{{поддомен}}**.

3. В этой статье будет использоваться заполнитель **{{siteUrl}}** — *URL-адрес* сайта или страницы, которую вы выбрали.
    - Примеры *URL-адресов*: https://contoso.sharepoint.com/teams/Contoso *или*   https://contoso.sharepoint.com/sites/Contoso 
4. Кроме того, **{{sitePath}}** будет использоваться для заметок URL *path* -адреса (например:/teams/Contoso).
    - Примеры *путей*:/teams/Contoso *или* /Sites/contoso 

Для начала выполните указанные ниже действия.

1. Перейдите в магазин Teams.

2. Установите или откройте приложение App Studio.

3. Нажмите кнопку **Открыть**рядом с параметром приложение.

4. В открытом приложении App Studio щелкните **редактор манифестов**.

5. **Создайте новое приложение**.

6. Заполните все **сведения о приложении**.

7. Щелкните **вкладки** в разделе "возможности".

8. Нажмите кнопку **Добавить** на вкладке Личные.

9. Введите **имя** и выберите **новый уникальный идентификатор сущности**.

10. Заполните **URL-адрес contentURL и веб-сайта**. 

- **contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx? SPFX = true&dest = {{sitePath}}  
- **websiteUrl**: {{siteUrl}} 

    Пример **contentURL**:https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub 

11. Перейдите в раздел **домены и разрешения**. Убедитесь, что в разделе Допустимые домены указаны доменные имена SharePoint Online.

    Пример: contoso.sharepoint.com

12. Добавьте следующие свойства **единого входа для** веб-приложения: 
     
     Пример: **ИД приложения AAD**: 00000003-0000-0Ff1-ce00-000000000000 **Resource URL**: {{поддомен}}. SharePoint. com

    ![Единый вход в веб-приложение с ИДЕНТИФИКАТОРом и URL-адресом.](media/personal-app.png)

13. **Сохраните** эти свойства, а затем перейдите к разделу **Проверка и распространение**. 

14. Установите приложение, чтобы протестировать приложение лично.

> [!IMPORTANT]
> Если вы не используете приложение Teams Studio, вам потребуется. zip манифест. JSON-файл, который вы только что создали, перейдите в магазин приложений в Teams и щелкните ссылку **Отправить настраиваемое приложение** (в правом нижнем углу магазина приложений). Это сделает приложение доступным для вас.

15. Теперь приложение доступно в виде статической вкладки для загрузки и просмотра в Teams.

## <a name="test-and-view-your-new-static-tab"></a>Проверка и просмотр новой статической вкладки

Чтобы открыть вкладку Создание на рабочем столе Teams, в левой части панели приложения перейдите на многоточие (**...**). Найдите новое приложение, загрузите его и протестируйте автономное приложение в Teams.

Если вы хотите сделать новое приложение доступным в меню слева в более высоком положении, необходимо использовать параметр политики приложения для этого. Этот параметр можно найти в разделе администратор группы > политики приложений > добавить закрепленное приложение. После назначения пользователю политики для тестирования это изменение будет отображаться на 24 часа позже. В этом случае необходимо решить, где должно отображаться приложение, чтобы избежать задержек.

Чтобы просмотреть и протестировать новое приложение на мобильном устройстве, откройте денежный ящик приложения, нажав значок шеврона**^**() над панелью вкладок в нижней части экрана. Найдите свое приложение и перейдите на него на мобильном устройстве.

> [!CAUTION]
> Поддержка мобильных устройств в настоящее время входит в предварительную версию для разработчиков. Чтобы включить предварительный просмотр для разработчика, перейдите к параметрам > о том, а затем включите режим предварительного просмотра разработчика.

## <a name="a-sample-manifestjson-file"></a>Пример файла manifest. JSON

Созданный вами JSON-файл будет выглядеть примерно так, как показано на рисунке ниже.

```JSON
{ 

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.5/MicrosoftTeams.schema.json", 

    "manifestVersion": "1.5", 

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

            "entityId": "communicationSiteTab", 

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