---
title: Управление предложением Microsoft Teams Exploratory
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: 'Пользователи Office 365, не имеющие лицензии на Microsoft Teams, могут воспользоваться лицензией на Teams Exploratory. '
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb0998579c29cd7405319600c436468bac2ec4e8
ms.sourcegitcommit: 73376693670d12f3d9038d4ed604e6685ee21984
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "41917024"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a>Управление лицензией на Microsoft Teams Exploratory
=======================================================

Предложение Microsoft Teams Exploratory позволяет пользователям в организации с Azure Active Directory (AAD), не имеющим лицензии на Teams, начать пробное использование Teams. Администраторы могут включать и отключать эту функцию для пользователей в организации. Предыдущее предложение [Microsoft Teams Commercial Cloud Trial](iw-trial-teams.md) теперь называется Teams Exploratory.

## <a name="whats-in-the-teams-exploratory-experience"></a>Что включает предложение Teams Exploratory?

Teams Exploratory включает следующие планы обслуживания:
 - Exchange Online (план 1)
 - Flow для Office 365
 - MyAnalytics для анализа данных
 - Microsoft Forms (план E1)
 - Планировщик (Майкрософт)
 - Поиск (Майкрософт)
 - Microsoft StaffHub
 - Microsoft Stream для номера SKU Office 365 E1
 - Microsoft Teams
 - Управление мобильными устройствами для Office 365
 - Приложения Office Mobile для Office 365 
 - Office Online
 - PowerApps для Office 365
 - SharePoint Online (план 1)
 - Sway
 - To-Do (план 1)
 - Доска (план 1)
 - Yammer корпоративный


## <a name="whos-eligible"></a>Кто имеет право на использование?

У пользователей есть возможность зарегистрироваться для получения приложений и пробных версий (в Центре администрирования Microsoft 365). Дополнительные сведения см. в разделе [Управление предложением Teams Exploratory](#manage-the-teams-exploratory-experience) далее в этой статье. 

Пользователи могут начать использование Teams Exploratory, если в их лицензию на Office 365 не входит Teams. Например, если у пользователя есть версия Office 365 бизнес (не включающая Teams), он имеет право на использование Teams Exploratory.

## <a name="who-isnt-eligible"></a>Кто не имеет права на использование?

Ваша организация не может использовать это предложение, если вы являетесь клиентом партнера по синдикации или клиентом GCC, GCC High, DoD либо EDU.


## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a>Регистрация для получения Teams Exploratory

Подходящие пользователи могут зарегистрироваться для получения предложения Teams Exploratory, выполнив вход на сайте Teams ([teams.microsoft.com](https://teams.microsoft.com)). Им будет автоматически назначена лицензия, и администратор клиента получит соответствующее уведомление по электронной почте, когда пользователь в организации в первый раз приступит к работе с Teams Exploratory.

## <a name="manage-the-teams-exploratory-experience"></a>Управление предложением Teams Exploratory

Предложение Teams Exploratory предназначено для активации отдельными пользователями, и вы не можете активировать его от имени сотрудников, являющихся конечными пользователями.

Предложение Teams Exploratory включает лицензию на Exchange Online, но она должна быть назначена пользователю администратором. Если у пользователя нет лицензии на Exchange и администратор еще не назначил лицензию на Exchange Online, пользователь не сможет планировать собрания в Teams и использовать другие функции Teams.

Администраторы могут отключить возможность использования Teams Exploratory для пользователей в своей организации с помощью переключателя **Пробные версии приложений и служб**.


### <a name="prevent-users-from-installing-trial-apps-and-services"></a>Запрет на установку пользователями пробных версий приложений и служб

Вы можете отключить возможность установки пробных версий приложений и служб, чтобы пользователи не могли использовать Teams Exploratory.

1. В [Центре администрирования Microsoft 365](https://portal.office.com/adminportal/home) выберите **Параметры** > **Параметры**, щелкните **Службы** и нажмите **Приложения и службы, лицензированные для отдельных пользователей**.

    ![Снимок экрана: страница "Службы" в Центре администрирования](media/iw-trial-services.png)

2. Снимите флажок **Разрешить пользователям устанавливать пробные версии приложений и служб**.

    ![Снимок экрана: страница "Приложения и службы, лицензированные для отдельных пользователей" в Центре администрирования](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > Если ваша организация не имеет права на использование Teams Exploratory, параметр **Разрешить пользователям устанавливать пробные версии приложений и служб** будет отсутствовать.

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a>Управление доступностью для пользователя с лицензией, включающей Teams

Пользователь, которому назначена лицензия, включающая Teams, не имеет права на использование Teams Exploratory. Если план обслуживания Teams включен, пользователь может выполнить вход и использовать Teams. Если план обслуживания отключен, пользователь не может выполнить вход и предложение Teams Exploratory недоступно для него.

Отключение доступа к Teams:

1. В Центре администрирования Microsoft 365 выберите **Пользователи** > **Активные пользователи**.

2. Установите флажок рядом с именем пользователя.

3. В правой части строки **Лицензии на продукты** щелкните ссылку **Изменить**.

4. В области **Лицензии на продукты** установите переключатель в положение **Выкл**.

    ![Снимок экрана: страница "Лицензии на продукты" в Центре администрирования.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a>Управление доступностью Teams для пользователей, уже использующих Teams Exploratory

Если пользователь использует предложение Teams Exploratory, вы можете отключить его, удалив лицензию или план обслуживания.

Чтобы отключить лицензию на Teams Exploratory, выполните указанные ниже действия.

1. В Центре администрирования Microsoft 365 выберите **Пользователи** > **Активные пользователи**.

2. Установите флажок рядом с именем пользователя.

3. В правой части строки **Лицензии на продукты** щелкните ссылку **Изменить**.

4. В области **Лицензии на продукты** установите переключатель для лицензии на это предложение в положение **Выкл**.
   
    >[!Note]
    >Переключатель для Teams Exploratory отобразится после того, как первый пользователь в организации запустит это предложение.

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a>Управление Teams для пользователей с лицензией на Teams Exploratory

Управление пользователями, у которых есть лицензия на Teams Exploratory, аналогично управлению пользователями с обычной платной лицензией. Дополнительные сведения см. в статье [Управление параметрами Teams в организации](enable-features-office-365.md).

### <a name="upgrade-users-from-the-teams-exploratory-license"></a>Перевод пользователей с лицензии на Teams Exploratory

Чтобы перевести пользователей с лицензии на Teams Exploratory, выполните указанные ниже действия.

1. Приобретите подписку, в которую входит Teams.

2. Удалите подписку пользователя на Teams Exploratory.

3. Назначьте приобретенную лицензию.

Дополнительные сведения см. в статье [Лицензирование Office 365 для Microsoft Teams](Office-365-licensing.md).

> [!NOTE]
> Если срок действия лицензии на Teams Exploratory окончился, а пользователь сразу не обновился до подписки, включающей Teams, пользовательские данные не будут удалены. Пользователь по-прежнему существует в Azure Active Directory, и все данные в Teams сохраняются. После назначения новой лицензии пользователю, чтобы повторно включить функции Teams, содержимое продолжит существовать. 

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a>Что произойдет с устаревшими лицензиями на Microsoft Teams Commercial Cloud Trial?

С середины января 2020 г. подходящие пользователи могут начать использование последней версии Microsoft Teams Exploratory. Все устаревшие лицензии на Teams Commercial Cloud Trial будут автоматически преобразованы в лицензии на новое предложение до истечения срока действия пробной версии.

### <a name="remove-a-teams-exploratory-license"></a>Удаление лицензии на Teams Exploratory

- Если вы хотите удалить эту лицензию с помощью PowerShell, см. статью [Использование PowerShell в Office 365 для удаления лицензий из учетных записей пользователей](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)

- Если вы хотите удалить эту лицензию на портале администрирования, см. статью [Удаление лицензий пользователей в Office 365 для бизнеса](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/remove-licenses-from-users?view=o365-worldwide)
