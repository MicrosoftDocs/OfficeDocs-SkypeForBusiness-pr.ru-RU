---
title: Управление предложением Microsoft Teams Exploratory
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: high
description: Пользователи Microsoft 365 или Office 365, не имеющие лицензии на Microsoft Teams, могут инициировать лицензию Exploratory Teams.
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5e5535be61aab03158aa11c68ebd3b753b3ca972
ms.sourcegitcommit: 18e66d54a9e349d4516253addc85cc12892c69a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2022
ms.locfileid: "68851779"
---
# <a name="manage-the-microsoft-teams-exploratory-license"></a>Управление лицензией на Microsoft Teams Exploratory

The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (Azure AD) and aren't licensed for Teams initiate an exploratory experience of Teams. Admins can switch this feature on or off for users in their organization.

## <a name="whats-in-the-teams-exploratory-experience"></a>Что включает предложение Teams Exploratory

Администратору будут представлены следующие планы обслуживания, входящие в предложение Teams Exploratory:

- Exchange Online (план 1)
- Flow для Microsoft 365 или Office 365
- MyAnalytics для анализа данных
- Microsoft Forms (план E1)
- Планировщик (Майкрософт)
- Поиск (Майкрософт)
- Microsoft StaffHub
- Microsoft Stream для SKU Microsoft 365 и Office 365 E1 <sup>1</1>
- Microsoft Teams
- Управление мобильными устройствами для Microsoft 365 или Office 365
- Приложения Office Mobile для Office 365
- Office Online
- Power Apps для Microsoft 365 или Office 365
- SharePoint Online (план 1)
- Sway
- To-Do (план 1)
- Доска (план 1)
- Yammer корпоративный

  <sup>1</sup> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach. At launch, you'll be able to opt in to this experience. In November, you'll have to opt out if you want to continue using Stream. Sometime in early 2021, we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.

## <a name="whos-eligible"></a>Кто имеет право на использование

Пользователи соответствуют критериям Teams Exploratory, если они:

- Имеют адрес электронной почты с управляемым доменом Azure AD.
- Входят в состав клиента с платной подпиской.
- У вас нет активной лицензии Teams.
- Не в клиенте, где была создана политика назначения лицензий.

Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center). For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.

## <a name="who-isnt-eligible"></a>Кто не имеет права на использование

Пользователи не соответствуют критериям, если они:

- Пользователи, у которых в настоящее время есть платная или пробная лицензия Teams, либо у которых ранее была пробная лицензия
- Входят в состав клиента, который использовал/получил по крайней мере одно специальное предложение, связанное с COVID.

Ваша организация не может использовать это предложение, если вы являетесь клиентом партнера по синдикации или клиентом GCC, GCC High, DoD либо EDU.

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a>Регистрация для получения Teams Exploratory

Подходящие пользователи могут зарегистрироваться для получения предложения Teams Exploratory, выполнив вход в Teams в классической или веб-версии ([teams.microsoft.com](https://teams.microsoft.com)). В настоящее время включение Exploratory через мобильные устройства не поддерживается. При регистрации ему будет назначена эта лицензия автоматически, и администратор клиента получит уведомление по электронной почте, когда кто-то в вашей организации впервые начнет работу с Teams Exploratory.

## <a name="manage-the-teams-exploratory-experience"></a>Управление предложением Teams Exploratory

Предложение Teams Exploratory предназначено для активации отдельными пользователями, и вы не можете активировать его от имени сотрудников, являющихся конечными пользователями.

The Teams Exploratory experience comes with an Exchange Online license, but it won't be assigned to the user until the admin assigns it. If the user doesn't have an Exchange license already, and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and might be missing other Teams functionality.

Администраторы могут отключить возможность использования Teams Exploratory для пользователей в своей организации с помощью переключателя **Пробные версии приложений и служб**.

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>Запрет на установку пользователями пробных версий приложений и служб

Вы можете отключить возможность установки пробных версий приложений и служб, чтобы пользователи не могли использовать Teams Exploratory.

1. В Центре администрирования Microsoft 365 выберите **Параметры** > **Параметры организации**, щелкните **Службы** и нажмите **Приложения и службы, лицензированные для отдельных пользователей**.

    ![страница "Службы" в Центре администрирования.](media/iw-trial-services.png)

2. Снимите флажок **Разрешить пользователям устанавливать пробные версии приложений и служб**.

    ![страница "Приложения и службы, лицензированные для отдельных пользователей" в Центре администрирования.](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > Если ваша организация не имеет права на использование Teams Exploratory, параметр **Разрешить пользователям устанавливать пробные версии приложений и служб** будет отсутствовать.

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a>Управление доступностью для пользователя с лицензией, включающей Teams

Пользователь, которому назначена лицензия, включающая Teams, не имеет права на использование Teams Exploratory. Если план обслуживания Teams включен, пользователь может выполнить вход и использовать Teams. Если план обслуживания отключен, пользователь не сможет войти в систему, а интерфейс Teams Exploratory недоступен. У вас должны быть права администратора.

Отключение доступа к Teams:

1. В Центре администрирования Microsoft 365 выберите **Пользователи** > **Активные пользователи**.

2. Установите флажок рядом с именем пользователя.

3. В правой части строки **Лицензии на продукты** щелкните ссылку **Изменить**.

4. В области **Лицензии на продукты** установите переключатель в положение **Выкл**.

    ![страница "Лицензии на продукты" в Центре администрирования.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a>Управление доступностью Teams для пользователей, уже использующих Teams Exploratory

If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan. You must have admin privileges.

Чтобы отключить лицензию на Teams Exploratory, выполните указанные ниже действия.

1. В Центре администрирования Microsoft 365 выберите **Пользователи** > **Активные пользователи**.

2. Установите флажок рядом с именем пользователя.

3. В правой части строки **Лицензии на продукты** щелкните ссылку **Изменить**.

4. В области **Лицензии на продукты** установите переключатель для лицензии на это предложение в положение **Выкл**.

    > [!NOTE]
    > Переключатель для Teams Exploratory отобразится после того, как первый пользователь в организации запустит это предложение.

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a>Управление Teams для пользователей с лицензией на Teams Exploratory

You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license. For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).

### <a name="upgrade-users-from-teams-exploratory"></a>Перевод пользователей с Teams Exploratory

Чтобы перевести пользователей с Teams Exploratory, у вас должны быть права администратора. Дополнительные сведения см. в разделе [Обновление пользователей с пробной версии Teams Exploratory](upgrade-from-teams-exploratory.md).

> [!NOTE]
> Если лицензия Teams Exploratory заканчивается и пользователь не будет немедленно обновлен до подписки, включающей Teams, он теряет доступ к Teams, OneDrive и Sharepoint после 30-дневного льготного периода. Еще через 30 дней связанные данные Teams, OneDrive и SharePoint удаляются. Пользователь по-прежнему будет существовать в Azure Active Directory.
> 
> После назначения новой лицензии пользователю, чтобы повторно включить функции Teams, содержимое продолжит существовать, если пользователь будет добавлен в течение льготного периода.

### <a name="remove-a-teams-exploratory-license"></a>Удаление лицензии на Teams Exploratory

- Если вы хотите удалить эту лицензию с помощью PowerShell, см. статью [Использование PowerShell в Office 365 для удаления лицензий из учетных записей пользователей](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)

- Если вы хотите удалить эту лицензию на портале администрирования, см. статью [Удаление пользователя из организации](/microsoft-365/admin/add-users/delete-a-user)

## <a name="what-is-the-data-retention-policy"></a>Что такое политика хранения данных

См. [Сведения о подписке на Microsoft 365](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires).

## <a name="how-long-does-the-teams-exploratory-experience-last"></a>Срок действия предложения Teams Exploratory

Версия Teams Exploratory доступна в качестве подписки на 12 месяцев (с первоначальной регистрации пользователя) для всех новых клиентов. Новая подписка на версию Teams Exploratory начинается, когда первый пользователь в организации регистрируется в Teams Exploratory, и истекает через 12 месяцев. Ко всем пользователям в одном клиенте применяется одинаковая дата окончания 12-месячного периода, который начинается с даты регистрации первого пользователя.

> [!NOTE]
> Дата окончания взаимодействия настраивается на уровне организации, то есть она будет применена ко всем пользователям в этой организации. Например, Пользователь 1 регистрирует подписку 1 января 2021 года. Это устанавливает дату окончания подписки — 31 декабря 2021 года. Другой пользователь, Пользователь 2, регистрирует подписку 1 октября 2021 года. Пользователь 2 может использовать версию Teams Exploratory в течение двух месяцев, так как дата окончания установлена на 31 декабря 2021 года, поскольку это подписка той же организации, что у Пользователя 1.

### <a name="what-should-administrators-do-at-the-end-of-the-12-month-teams-exploratory-experience"></a>Что следует сделать администраторами по окончании 12 месяцев использования версии Teams Exploratory

По окончании подписки на 12 месяцев администраторам следует перевести всех пользователей версии Teams Exploratory на платную лицензию, в которую входит Microsoft Teams. Очень важно убедиться, что это действие будет завершено до истечения срока действия подписки Teams Exploratory, чтобы избежать каких-либо нарушений взаимодействия с пользователем.


> [!NOTE]
> Возможность запуска клиентами новых лицензий на пробную версию Exploratory будет отключена и заблокирована в течение 3 месяцев после истечения срока действия предыдущей лицензии на пробную версию Exploratory.

Дополнительные сведения см. в разделе [Перевод пользователей с Teams Exploratory](#upgrade-users-from-teams-exploratory) выше в этой статье.
