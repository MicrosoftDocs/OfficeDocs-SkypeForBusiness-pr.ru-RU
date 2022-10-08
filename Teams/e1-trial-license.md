---
title: Управление бесплатной пробной версией Office 365 E1
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
audience: Admin
ms.reviewer: aytange
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: high
description: Если у вас нет приложения Microsoft Teams и оно срочно вам требуется, разверните пробную версию Office 365 E1 для своих пользователей, которым нужно работать удаленно или из дома в связи со вспышкой эпидемии COVID-19 (коронавируса).
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b920d004fde707a399ee4b0383d7dcba985f6d3c
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377357"
---
# <a name="manage-the-office-365-e1-trial"></a>Управление пробной версией Office 365 E1

С 1 июля 2020 г. лицензия на пробную версию Office 365 E1 больше не доступна. Если вам нужно назначить пользователям лицензии на Microsoft Teams, см. статью [Описание службы Microsoft Teams](/office365/servicedescriptions/teams-service-description), где приведен список платных подписок, включающих Teams. Кроме того, соответствующие организации могут использовать **[бесплатную версию Teams](https://support.office.com/article/Welcome-to-Microsoft-Teams-free-6d79a648-6913-4696-9237-ed13de64ae3c)** или сотрудники могут активировать интерфейс **[Teams Exploratory](teams-exploratory.md)**.

Если вы используете Teams для образования, проверьте наличие бесплатной [лицензии Office 365 A1](teams-edu-licensing.md).

Используйте инструкции, приведенные в этой статье, для управления существующими лицензиями на пробную версию Office 365 E1, включая [обновление до платной подписки](#upgrade-users-from-the-office-365-e1-trial-license).

Не пропустите наши рекомендации по [поддержке удаленных сотрудников в Teams](support-remote-work-with-teams.md).

## <a name="manage-the-e1-trial"></a>Управление пробной версией E1

После активации пробной версии Office 365 E1 включите лицензию для всех пользователей, которым она требуется. Сведения о том, как это сделать, см. в статье [Управление доступом пользователей к Teams](user-access.md).


Once you've turned on the E1 Trial for the users who need it, you'll manage these users just like you manage users who have a paid license. For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).



### <a name="upgrade-users-from-the-office-365-e1-trial-license"></a>Переход пользователей с пробной лицензии Office 365 E1

Чтобы перевести пользователей пробной версии E1 на платную подписку:

1. Приобретите подписку, в которую входит Teams.

2. Удалите пробную подписку пользователя на Office 365 E1.

3. Назначьте приобретенную лицензию.

Для получения дополнительной информации см. [Описание службы Microsoft Teams](/office365/servicedescriptions/teams-service-description).

> [!NOTE]
> If the E1 Trial license ends and a user is not immediately upgraded to a subscription that includes Teams, the user data is not removed. The user still exists in Azure Active Directory and all data within Teams still remains. Once a new license is assigned to the user to enable Teams functionality again, all content will still exist. 

### <a name="remove-an-office-365-e1-trial-license"></a>Удаление лицензии на пробную версию Office 365 E1

- Если вы хотите удалить эту лицензию с помощью PowerShell, см. статью [Использование PowerShell в Office 365 для удаления лицензий из учетных записей пользователей](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)

- Если вы хотите удалить эту лицензию на портале администрирования, см. статью [Удаление пользователя из организации](/microsoft-365/admin/add-users/delete-a-user)

## <a name="related-topics"></a>Связанные статьи

[Управление доступом пользователей к Teams](user-access.md)

[Управление параметрами Teams в организации](enable-features-office-365.md)

[Управление предложением Teams Exploratory](teams-exploratory.md)

[Microsoft 365 или Office 365 для некоммерческих организаций](https://www.microsoft.com/microsoft-365/nonprofit/office-365-nonprofit)

[Получение помощи с развертыванием Teams](https://go.microsoft.com/fwlink/?linkid=780698)