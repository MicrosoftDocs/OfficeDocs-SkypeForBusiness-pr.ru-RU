---
title: Добавление, изменение и удаление мест для точек экстренного реагирования
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: Сведения о том, как добавлять, изменять и удалять место для экстренных случаев для Организации в центре администрирования Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c3ff180848d12ad3fb00d048bbb1910bf13c00d6
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232500"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>Добавление, изменение и удаление места для расположения для экстренного реагирования для организации

В зависимости от количества физических местоположений в вашей организации вы можете добавить места для зданий, полs и офисов, чтобы создать более конкретное место для экстренных случаев. Более подробную информацию вы видите в разделе [Управление вызовом экстренной](what-are-emergency-locations-addresses-and-call-routing.md) помощи.
  
Сведения о том, как получить план звонков и затраты на него, можно найти [в разделе Лицензирование надстроек для Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

Вы управляете местоположениями для экстренного реагирования для вашей организации в центре администрирования Microsoft Teams или с помощью PowerShell.
  
## <a name="add-a-place-to-an-emergency-location"></a>Добавление места в место для экстренного реагирования

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации центра администрирования Microsoft Teams **выберите пункты**  >  **адреса для экстренного**реагирования.
2. В списке щелкните имя расположения, для которого вы хотите добавить место.
3. На вкладке **места** нажмите кнопку **Добавить место**.
4. Введите имя места, а затем нажмите кнопку **Применить**.

### <a name="using-powershell"></a>Использование PowerShell

Просмотреть раздел [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).
    
## <a name="change-a-place-for-an-emergency-location"></a>Изменение места для экстренных случаев

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации центра администрирования Microsoft Teams **выберите пункты**  >  **адреса для экстренного**реагирования.
2. В списке щелкните имя расположения, для которого вы хотите изменить место.
3. На вкладке **места** выберите место, которое вы хотите изменить, и нажмите кнопку **изменить**.
4. Обновите сведения о расположении и нажмите кнопку **Применить**.

### <a name="using-powershell"></a>Использование PowerShell

Смотрите раздел [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).
    
## <a name="remove-a-place-from-an-emergency-location"></a>Удаление места из места для экстренного реагирования

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации центра администрирования Microsoft Teams **выберите пункты**  >  **адреса для экстренного**реагирования.
2. В списке щелкните имя расположения, для которого нужно удалить место.
3. На вкладке **места** выберите место, которое вы хотите удалить, и нажмите кнопку **Удалить**.

### <a name="using-powershell"></a>Использование PowerShell

В разделе [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).
    
## <a name="related-topics"></a>Статьи по теме

- [Добавление, изменение и удаление места для расположения для экстренного реагирования для организации](add-change-remove-emergency-place-organization.md)
- [Управление номерами телефонов организации](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Условия и положения, распространяющиеся на экстренные вызовы](/microsoftteams/emergency-calling-terms-and-conditions)
