---
title: Добавление, изменение и удаление мест для экстренного размещения
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Узнайте, как добавить, изменить или удалить место для экстренного размещения для вашей организации в центре Microsoft Teams администрирования.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 98135be7b74583ad01718d19796889bdc9a467d1
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2021
ms.locfileid: "60537220"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>Добавление, изменение и удаление места для расположения для экстренного реагирования для организации

В зависимости от количества физических расположений в организации вы можете добавить места для зданий, этажей и офисов, чтобы создать более конкретное местоположение для экстренного нахождения. Дополнительные [сведения см.](what-are-emergency-locations-addresses-and-call-routing.md) в управлении звонками на экстренные вызовы.

Вы управляете местоположениями для экстренного экстренного ситуация в Microsoft Teams центре администрирования или с помощью PowerShell.
  
## <a name="add-a-place-to-an-emergency-location"></a>Добавление места для экстренного размещения

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **Адреса** для экстренного  >  **устранения чрезвычайной ситуации**.
2. В списке выберите расположение, для которого вы хотите добавить место.
3. На **вкладке** Места нажмите кнопку **Добавить**.
4. Введите имя места и нажмите кнопку **Применить**.

### <a name="using-powershell"></a>С помощью PowerShell

См. [new-CsOnlineLisLocation](/powershell/module/skype/new-csonlinelislocation).
    
## <a name="change-a-place-for-an-emergency-location"></a>Изменение места для экстренного размещения

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **Адреса** для экстренного  >  **устранения чрезвычайной ситуации**.
2. В списке выберите расположение, для которого вы хотите изменить место.
3. На **вкладке** Места выберите место, которое вы хотите изменить, и нажмите кнопку **Изменить**.
4. Обновив сведения о месте, нажмите кнопку **Применить**.

### <a name="using-powershell"></a>С помощью PowerShell

См. [set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).
    
## <a name="remove-a-place-from-an-emergency-location"></a>Удаление места из местоположения для экстренного устранения чрезвычайной ситуации

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **Адреса** для экстренного  >  **устранения чрезвычайной ситуации**.
2. В списке выберите расположение, для которого вы хотите удалить место.
3. На **вкладке** Места выберите место, которое нужно удалить, и нажмите кнопку **Удалить**.

### <a name="using-powershell"></a>С помощью PowerShell

См. [remove-CsOnlineLisLocation](/powershell/module/skype/remove-csonlinelislocation).
    
## <a name="related-topics"></a>Статьи по теме

- [Добавление, изменение и удаление места для расположения для экстренного реагирования для организации](add-change-remove-emergency-place-organization.md)
- [Управление номерами телефонов организации](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Условия и положения, распространяющиеся на экстренные вызовы](./emergency-calling-terms-and-conditions.md)