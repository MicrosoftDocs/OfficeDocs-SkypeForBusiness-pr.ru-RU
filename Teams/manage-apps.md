---
title: Управление приложениями в центре Microsoft Teams администрирования
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: vaibhava
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Узнайте, как управлять приложениями Teams на странице "Управление приложениями" Microsoft Teams центра администрирования.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 2a4062bbf71c3ad112a52a10ad9c1b3ff71f3dad
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059080"
---
# <a name="manage-teams-apps-in-the-microsoft-teams-admin-center"></a>Управление Teams приложениями в Microsoft Teams администрирования

Вы управляете приложениями для своей **организации в Teams приложениях** в Центре администрирования. Страница "[Управление приложениями](https://admin.teams.microsoft.com/policies/manage-apps)" используется для просмотра Teams приложений в каталоге приложений вашей организации и управления ими. На странице "Управление приложениями" вы можете просмотреть все доступные приложения в каталоге клиента, указав сведения, необходимые для выбора приложений, которые следует разрешить или заблокировать в организации. Вы можете просматривать состояние и свойства приложений на уровне организации, блокировать или разрешать приложения на уровне организации, отправлять новые настраиваемые приложения в каталог клиента и управлять параметрами приложений на уровне организации.

![Снимок экрана: страница "Управление приложениями".](media/manage-apps.png)

Чтобы использовать Teams администрирования, необходимо быть глобальным администратором или администратором Teams службы. Дополнительные сведения см[. в Teams роли администратора](./using-admin-roles.md).

Для управления приложениями используются политики для управления разрешениями для пользователей, установки приложений и отправки пользовательских приложений, созданных в организации. Сведения о политиках см [. в разделе "Общие сведения о политиках приложений"](app-policies.md).

> [!NOTE]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

> [!NOTE]
> Страница "Управление приложениями" недоступна в развертываниях Microsoft 365 облако сообщества для государственных организаций (GCCH) или Министерства обороны Сша (DoD) Teams.

<!--- TBD: This info belongs in the app policy overview article. Title it as mentioned in the spreadsheet.

* **App permission policy**: With it, you can control what apps are available to specific users in your organization. You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization. See [Manage app permission policies in Teams](teams-app-permission-policies.md).
* **App setup policies**: It lets you customize the app experience for your users. You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients. See [Manage app setup policies in Teams](teams-app-setup-policies.md).
* **Custom app policies and settings**: Teams allows developers in your organization to build, test, and deploy custom apps to other users. Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context. You can use app setup policies to control who in your organization can upload custom apps. You can also set org-wide settings to control whether users can interact with specific custom apps. See [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings).

The following are the important use cases you can accomplish via the the Manage apps page:

* [Allow or block apps at the org level](#allow-and-block-apps)
* [Apps blocked by publishers](#apps-blocked-by-publishers)
* [Add apps to teams](#add-an-app-to-a-team)
* [Approve or upload new custom apps to your organization's app store](#publish-a-custom-app-to-your-organizations-app-store)
* [View permissions requested by apps](#view-resource-specific-consent-permissions)
* [Grant consent to apps](#grant-admin-consent-to-apps)
* [Purchase service for third-party apps](#purchase-services-for-third-party-apps)
* [See org-level status and properties of apps](#view-apps)
* [Manage org-wide app settings](#manage-org-wide-app-settings)
* [View security and compliance information for Microsoft 365 Certified apps](#view-security-and-compliance-information-for-microsoft-365-certified-apps)

<!--- TBD: Commenting for now in favor of the definition list above: 

The Manage apps page gives you a view into all available apps, providing you with the information you need to decide which apps to allow or block across your organization. You can then use [app permission policies](teams-app-permission-policies.md), [app setup policies](teams-app-setup-policies.md), and [custom app policies and settings](teams-custom-app-policies-and-settings.md) to configure the app experience for specific users in your organization.

In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**. You must be a global admin or Teams service admin to access the page.

--->

<!--- TBD: Move this view apps section to a new article about navigating and understanding TAC. It is yet to be created.

## View apps

You can view every app including the following information about each app.

![Screenshot of the apps details page for an app.](media/app-detail-page.jpg)

- **Name**: The app name. Select the app name to go to the app details page to see more information about the app. This includes a description of the app, whether it's allowed or blocked, version, privacy policy, terms of use, categories that apply to the app, certification status, supported capabilities, and app ID.
- **Certification**: If the app has gone through certification, you'll see either **Microsoft 365 certified** or **Publisher attestation**. Select the link to view certification details for the app. If you see `--`, we don't have certification information for the app. To learn more about certified apps in Teams, read [Microsoft 365 App Certification program](/microsoft-365-app-certification/overview).
- **Publisher**: Name of the publisher.
- **Publishing status**: Publishing status of custom apps.
- **Status**: Status of the app at the org level, which can be one of the following:
  - **Allowed**: The app is available for all users in your organization.
  - **Blocked**: The app is blocked and not available for any users in your organization.
  - **Blocked by publisher**: The app is blocked by the publisher and is hidden from end-users by default. After you set up the app using the publisher's guidance, you can allow or block the app to make it available to end-users.
  - **Blocked org-wide**: The app is blocked in org-wide app settings.
      It's important to know that this column represents the allowed and blocked status of apps that were formerly on the **Org-wide settings** pane. You now view, block, and allow apps at the org-wide on the **Manage apps** page.
- **Licenses**: Indicates whether an app offers a Software as a Service (SaaS) subscription for purchase. This column applies only to third-party apps. Each third-party app will have one of the following values:
  - **Purchase**: The app offers a SaaS subscription and is available to purchase.  
  - **Purchased**: The app offers a SaaS subscription and you've purchased licenses for it.
  - **- -**: The app doesn't offer a SaaS subscription.
- **Custom app**: Whether the app is a custom app.
- **Permissions**: Indicates whether a third-party or custom app that's registered in Azure Active Directory (Azure AD) has permissions that need consent. You'll see one of the following values:
  - **View details**: The app has permissions that require consent before the app can access data.
  - **- -**: The app doesn't have permissions that need consent.
- **Categories**: Categories that apply to the app.
- **Version**: App version.
- **Admin can install in meetings**: Indicates whether an app can be installed by admins in Team meetings. [Learn more](teams-app-setup-policies.md#install-apps)

To see the information that you want in the table, select **Edit Column** in the upper-right corner to add or remove columns to the table.
--->

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>Публикация пользовательского приложения в магазине приложений организации

Страница "Управление приложениями" используется для публикации приложений, созданных специально для вашей организации. После публикации пользовательского приложения оно будет доступно пользователям в магазине приложений вашей организации. Существует два способа публикации пользовательского приложения в магазине приложений вашей организации. Способ использования зависит от способа получения приложения.

* [Утверждение пользовательского приложения](#approve-a-custom-app). Используйте этот метод, если разработчик отправляет приложение непосредственно на страницу "Управление приложениями" с помощью Teams API отправки приложения. Затем вы можете просмотреть и опубликовать (или отклонить) приложение непосредственно на странице сведений о приложении.
* [Upload пакет приложения](#upload-an-app-package). Используйте этот метод, если разработчик отправляет вам пакет приложения в .zip формате. Вы публикуете приложение, загружая пакет приложения.

### <a name="approve-a-custom-app"></a>Утверждение пользовательского приложения

**Мини-приложение "** Ожидающие утверждения" на странице "Управление приложениями" уведомляет вас, когда разработчик отправляет приложение с помощью API отправки Teams приложения. Вновь отправленное приложение отображается с состоянием публикации **"Отправлено**" и состоянием  **"Заблокировано"**. Перейдите на страницу сведений о приложении, чтобы просмотреть дополнительные сведения о приложении,  а затем опубликуйте его, задав для состояния публикации **значение "Опубликовать"**.

Вы также будете уведомлены, когда разработчик отправляет обновление в пользовательское приложение. Затем можно просмотреть и опубликовать (или отклонить) обновление на странице сведений о приложении. Все политики разрешений приложений и политики установки приложений остаются обязательными для обновленного приложения.

Дополнительные сведения см. в статье [о публикации](submit-approve-custom-apps.md) пользовательского приложения, отправленного через API отправки Teams приложения.

### <a name="upload-an-app-package"></a>Upload пакет приложения

Разработчик создает пакет Teams с помощью [Teams App Studio](/microsoftteams/platform/get-started/get-started-app-studio), а затем отправляет его вам в .zip формате. Если у вас есть пакет приложения, его можно отправить в магазин приложений вашей организации.

Чтобы отправить новое пользовательское приложение, **выберите Upload,** чтобы отправить пакет приложения. Приложение не выделяется после его отправки, поэтому вам потребуется выполнить поиск по списку приложений на странице "Управление приложениями", чтобы найти его.

Чтобы обновить приложение после его отправки, в списке приложений на странице "Управление приложениями" выберите имя приложения и нажмите кнопку **"Обновить"**. Это заменяет существующее приложение, и все политики разрешений приложений и политики установки приложений остаются обязательными для обновленного приложения.

Дополнительные сведения см. [в статье "Публикация пользовательского приложения путем отправки пакета приложения"](upload-custom-apps.md).

## <a name="allow-and-block-apps"></a>Разрешение и блокировка приложений

На странице "Управление приложениями" можно разрешить или заблокировать отдельные приложения на уровне организации. Здесь отображаются все доступные приложения и текущее состояние приложения на уровне организации. (Блокировка и разрешение приложений на уровне организации перемещены из области параметров  приложения для всей организации в область "Здесь".)

Чтобы разрешить или заблокировать приложение, выберите его, а затем выберите " **Разрешить"** или " **Блокировать"**. При блокировке приложения все взаимодействия с этим приложением отключаются, и оно не отображается в Teams для пользователей в вашей организации.

При блокировке или разрешении приложения на странице "Управление приложениями" это приложение блокируется или разрешается для всех пользователей в организации.  Если вы блокируете или разрешаете приложение в политике разрешений Teams, оно блокируется или разрешается пользователям, которым назначена эта политика. Чтобы пользователь был в состоянии установить любое приложение и взаимодействовать с ним, необходимо разрешить приложение на уровне организации на странице "Управление приложениями" и в политике разрешений приложения, назначенной пользователю.

 > [!NOTE]
 > Чтобы удалить приложение, щелкните его правой кнопкой мыши, а затем выберите команду "Удалить" или воспользуйтесь меню "Другие приложения" слева.

## <a name="apps-blocked-by-publishers"></a>Приложения, заблокированные издателями

Когда независимый поставщик программного обеспечения публикует приложение в глобальном магазине приложений, администраторам может потребоваться настроить или настроить интерфейс приложения. Администратор может сделать его доступным для конечных пользователей, когда приложение полностью настроено.

Например, Contoso Electronics — это независимый поставщик программного обеспечения, который создает приложение службы технической поддержки для Microsoft Teams. Компания Contoso Electronics хочет, чтобы ее клиенты настроили определенные свойства приложения, чтобы при взаимодействии пользователей с приложением оно функционирует должным образом. Прежде чем администратор сможет разрешить или заблокировать приложение, оно будет отображаться как  заблокированное издателем в центре администрирования Teams и по умолчанию будет скрыто от конечных пользователей. Следуя указаниям издателя по настройке приложения, вы можете сделать его доступным для пользователей, изменив состояние на "Разрешено **", или** запретить пользователям использовать приложение, изменив состояние на **"Заблокировано"**.

![Снимок экрана: заблокировано состоянием издателя в Центре администрирования teams.](media/blocked-by-publisher.png)

## <a name="add-an-app-to-a-team"></a>Добавление приложения в команду

Чтобы установить **приложение** для команды, используйте кнопку "Добавить в команду". Помните, что это предназначено только для приложений, которые можно установить в области группы. **Кнопка "Добавить в команду**" недоступна для приложений, которые можно установить только в личной области.

![Снимок экрана: кнопка "Добавить в команду".](media/manage-apps-add-app-team.png)

1. Найдите нужное приложение и выберите его, щелкнув его слева от имени приложения.
1. Выберите **"Добавить в команду"**.
1. На панели "Добавить в **группу** " найдите команду, в которую вы хотите добавить приложение, выберите команду и нажмите кнопку "Применить **"**.

## <a name="customize-an-app"></a>Настройка приложения

Теперь вы можете настроить приложение, включив в него определенный внешний вид в соответствии с потребностями вашей организации. См[. раздел "Настройка приложений в Teams](customize-apps.md)".

## <a name="purchase-services-for-third-party-apps"></a>Приобретение служб для сторонних приложений

Вы можете искать и приобретать лицензии на службы, предлагаемые сторонними приложениями для пользователей в организации, непосредственно на странице "Управление приложениями". **Столбец "Лицензии**" в таблице указывает, предлагает ли приложение платную подписку SaaS. Выберите **"Приобрести сейчас** ", чтобы просмотреть планы и сведения о ценах, а также приобрести лицензии для пользователей. Дополнительные сведения см. в статье "Приобретение Teams сторонних приложений [в центре Microsoft Teams администрирования"](purchase-third-party-apps.md).

## <a name="grant-admin-consent-to-apps"></a>Предоставление согласия администратора для приложений

Вы можете просмотреть и предоставить согласие приложениям, которые запрашивают разрешения от имени всех пользователей в организации. Это необходимо для того, чтобы пользователям не нужно было просматривать и принимать разрешения, запрашиваемые приложением при запуске приложения. В **столбце "** Разрешения" указывается, имеет ли приложение разрешения, для которых требуется согласие. Вы увидите ссылку " **Просмотреть сведения** " для каждого приложения, зарегистрированного в Azure AD, с разрешениями, которые требуют согласия. Дополнительные сведения см. в разделе "Просмотр разрешений приложения" и предоставление согласия администратора [в центре Microsoft Teams администрирования](app-permissions-admin-center.md).

## <a name="view-resource-specific-consent-permissions"></a>Просмотр разрешений на согласие для конкретных ресурсов

Разрешения на согласие для конкретных ресурсов (RSC) позволяют владельцам команд предоставлять приложению согласие на доступ к данным команды и изменять их. Разрешения RSC детализированные, Teams, которые определяют, что приложение может делать в определенной команде. Разрешения RSC можно просмотреть на **вкладке "** Разрешения" на странице сведений о приложении. Дополнительные сведения см. в разделе "Просмотр разрешений приложения" и предоставление согласия администратора [в центре Microsoft Teams администрирования](app-permissions-admin-center.md).

## <a name="manage-org-wide-app-settings"></a>Управление параметрами приложений для всей организации

Используйте параметры приложения для всей организации, чтобы контролировать, получают ли пользователи с лицензией [F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) специализированное интерфейсное приложение, могут ли пользователи устанавливать сторонние приложения и могут ли пользователи отправлять пользовательские приложения в организации или взаимодействовать с ними. Параметры приложения в пределах организации определяют поведение всех пользователей и переопределяют любые другие политики разрешений для приложений, назначенных пользователям. Их можно использовать для управления вредоносными или проблемными приложениями.

> [!NOTE]
> Сведения об использовании параметров приложений для всей организации в развертываниях Microsoft 365 для государственных организаций — облако сообщества для государственных организаций High GCCH и Министерства обороны Сша (DoD) Teams см. в статье ["](teams-app-permission-policies.md)Управление политиками разрешений приложений" в Teams.

1. На странице "Управление приложениями" выберите **параметры приложения для всей организации**. Затем можно настроить нужные параметры в области.

    :::image type="content" source="media/manage-apps-org-wide-app-settings.png" alt-text="Снимок экрана: панель параметров приложения для всей организации на странице &quot;Управление приложениями&quot;":::

1. В **разделе "Специализированные приложения**" отключите или включите **отображение специализированных приложений**. Если этот параметр включен, пользователи с лицензией [F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) получают специализированное интерфейсное приложение. Этот интерфейс закрепляет наиболее релевантные приложения в Teams для сотрудников без компьютеров. Дополнительные сведения см. [в Teams приложениях для сотрудников без компьютеров](pin-teams-apps-based-on-license.md).

    Эта функция доступна для лицензий F. Другие типы лицензий будут поддерживаться в будущем.
1. В разделе **Сторонние приложения**, отключите и включите эти параметры для управления доступом к сторонним программам:

    - **Разрешить приложениям сторонних разработчиков**: Определяет, могут ли пользователи использовать приложения сторонних разработчиков. Если отключить этот параметр, пользователи не смогут устанавливать или использовать сторонние приложения, а их состояние отображается в таблице как заблокированное на уровне организации.

        > [!NOTE]
        > Если разрешение сторонних приложений отключено [,](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) исходящие веб-перехватчики по-прежнему включены для всех пользователей, но вы можете управлять ими на уровне пользователя, разрешая или блокируя исходящее приложение **веб-перехватчика** с помощью политик разрешений [приложения.](teams-app-permission-policies.md) Обратите внимание, что если у вас есть существующие политики  разрешений для приложений Майкрософт, которые используют параметр "Разрешить определенные приложения" и блокируют все остальные, и вы хотите включить исходящие веб-перехватчики для пользователей, добавьте в список приложение исходящего веб-перехватчика.[](teams-app-permission-policies.md)

        > [!NOTE]
        > Пользователи Teams могут добавлять приложения, когда они проводят собрания или чаты с пользователями из других организаций. Они также могут использовать приложения, предоставленные пользователями из других организаций, когда они присоединяются к собраниям или чатам, проводимым в этих организациях. Применяются политики данных организации пользователя узла, а также методы совместного использования данных сторонних приложений, предоставленных организацией этого пользователя.

    - **Разрешить любые новые сторонние приложения, опубликованные в магазине по умолчанию**: Определяет, будут ли новые сторонние приложения, опубликованные в магазине приложений Teams, автоматически доступны в Teams. Этот параметр доступен только, если разрешено использование приложений сторонних разработчиков.

1. В **разделе "Пользовательские** приложения" отключите или включите разрешение **взаимодействия с пользовательскими приложениями**. Этот параметр определяет, могут ли пользователи взаимодействовать с пользовательскими приложениями. Дополнительные сведения см. в статье [Управление политиками и параметрами пользовательских приложений в Teams](teams-custom-app-policies-and-settings.md).
1. Нажмите **кнопку "** Сохранить", чтобы параметры приложения для всей организации вступает в силу.

<!--- TBD: Commenting this info for now. Move it later to the new article about compliance program and how/where admins can find info about compliant apps.

## View security and compliance information for Microsoft 365 Certified apps

When evaluating an app for their organization, admins can use independent Cloud Access Security Brokers (CASB), such as Microsoft Cloud App Security (MCAS), to find information about security and behaviors of an app. The Teams admin center includes security and compliance information from MCAS for Microsoft 365 Certified apps so you'll have more information on whether or not the app meets your needs.

> [!NOTE]
> This feature is available to all admins, whether or not your organization has a license that supports MCAS.

To access MCAS information, follow these steps:

1. In the Teams admin center, select **Manage apps** under **Teams apps**.
1. Select **Certification** to sort apps and push all Microsoft 365 Certified apps to the top of the table.
1. Choose a Microsoft 365 Certified app.
1. Select the **Security and compliance** tab.

![Screenshot of Teams admin center security and compliance tab.](media/mcas.png)

On this tab, you'll find information on security, compliance, and data protection. You can also expand each dropdown list to get more details about which capabilities are supported for the selected application.
--->
