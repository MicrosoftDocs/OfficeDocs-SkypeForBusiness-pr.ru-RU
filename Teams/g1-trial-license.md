---
title: Управление бесплатной пробной версией Office 365 G1 для государственных учреждений США
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
audience: Admin
ms.reviewer: aarimm
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: high
description: 'Для государственных учреждений США: если у вас нет приложения Microsoft Teams и оно срочно вам требуется, разверните пробную версию Office 365 G1 для своих пользователей, которым нужно работать удаленно или из дома в связи со вспышкой эпидемии COVID-19 (коронавируса).'
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: beb8537fe77549b9cb6d74c7b8958ba117eb06bc
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562558"
---
# <a name="manage-the-office-365-g1-trial-for-us-government"></a>Управление пробной версией Office 365 G1 для государственных учреждений США 

С 1 июля 2020 г. лицензия на пробную версию Office 365 E1 больше не доступна. Если вам нужно назначить пользователям лицензии на Microsoft Teams, см. статью [Описание службы Microsoft Teams](/office365/servicedescriptions/teams-service-description), где приведен список платных подписок, включающих Teams. 

Используйте инструкции, приведенные в этой статье, для управления существующими лицензиями на пробную версию Office 365 G1, в том числе для [обновления до платной подписки](#upgrade-users-from-the-office-365-g1-trial-license). Подробнее см. в разделах [Планы Microsoft 365 для государственных учреждений](https://www.microsoft.com/microsoft-365/government/compare-office-365-government-plans) и [Возможности Microsoft Teams, доступные в облаке GCC](plan-for-government-gcc.md).

Не пропустите наши рекомендации по [поддержке удаленных сотрудников в Teams](support-remote-work-with-teams.md).

## <a name="manage-the-g1-trial"></a>Управление пробной версией G1

После активации пробной версии Office 365 G1 включите лицензию для всех пользователей, которым она требуется. Сведения о том, как это сделать, см. в статье [Управление доступом пользователей к Teams](user-access.md).

После включения пробной версии G1 для пользователей, которым она требуется, вы сможете управлять ими так же, как управляете пользователями с платной лицензией. Дополнительные сведения см. в статье [Управление параметрами Teams в организации](enable-features-office-365.md).

### <a name="upgrade-users-from-the-office-365-g1-trial-license"></a>Переход пользователей с пробной лицензии Office 365 G1

Чтобы перевести пользователей пробной версии G1 на платную подписку:

1.  Приобретите подписку, в которую входит Teams.

2.  Удалите пробную подписку пользователя на Office 365 G1.

3.  Назначьте приобретенную лицензию.

Дополнительные сведения см. в статье [Teams для государственных учреждений](expand-teams-across-your-org/teams-for-government-landing-page.md).

> [!NOTE]
> Если срок действия пробной лицензии G1 истек, а пользователь сразу не обновился до подписки, включающей Teams, пользовательские данные не удаляются. Пользователь по-прежнему существует в Azure Active Directory, а все данные в Teams сохраняются. Содержимое продолжит существовать, чтобы повторно включить функции Teams после назначения новой лицензии пользователю.
> 
### <a name="remove-an-office-365-g1-trial-license"></a>Удаление лицензии на пробную версию Office 365 G1

  - Если вы хотите удалить эту лицензию с помощью PowerShell, см. статью [Использование PowerShell в Office 365 для удаления лицензий из учетных записей пользователей](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)

  - Если вы хотите удалить эту лицензию на портале администрирования, см. статью [Удаление пользователя из организации](/microsoft-365/admin/add-users/delete-a-user)

## <a name="related-topics"></a>Связанные статьи

[Управление доступом пользователей к Teams](user-access.md)

[Управление параметрами Teams в организации](enable-features-office-365.md)
