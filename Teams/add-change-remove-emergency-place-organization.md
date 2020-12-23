---
title: Добавление, изменение и удаление мест для экстренного размещения
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
description: Узнайте, как добавить, изменить или удалить расположение для экстренного решения для вашей организации в Центре администрирования Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5ba712602ef2a966343282d4e467365f3c1c3329
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539436"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>Добавление, изменение и удаление места для расположения для экстренного реагирования для организации

В зависимости от числа физических расположений в организации вы можете добавить здания, этажи и офисы, чтобы создать более конкретное местоположение для экстренного нахождения. Дополнительные [сведения см. в подмносях "Управление](what-are-emergency-locations-addresses-and-call-routing.md) экстренным вызовом".
  
Чтобы узнать, как получить план звонков и сколько они стоят, см. лицензирование [надстройки Teams.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

Вы управляете местоположениями в организации в Центре администрирования Microsoft Teams или с помощью PowerShell.
  
## <a name="add-a-place-to-an-emergency-location"></a>Добавление места для экстренного нахождения

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **адреса** для экстренного  >  **устранения экстренных служб.**
2. В списке щелкните название расположения, для которого вы хотите добавить место.
3. На вкладке **"Места"** нажмите кнопку **"Добавить".**
4. Введите имя места и нажмите кнопку **"Применить".**

### <a name="using-powershell"></a>С помощью PowerShell

См. [new-CsOnlineLisLocation.](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation)
    
## <a name="change-a-place-for-an-emergency-location"></a>Изменение места для экстренного размещения

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **адреса** для экстренного  >  **устранения экстренных служб.**
2. В списке щелкните имя расположения, для которого вы хотите изменить место.
3. На **вкладке "Места"** выберите место, которое нужно изменить, и нажмите кнопку **"Изменить".**
4. Обновив сведения о месте, нажмите кнопку **"Применить".**

### <a name="using-powershell"></a>С помощью PowerShell

См. [set-CsOnlineLisLocation.](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)
    
## <a name="remove-a-place-from-an-emergency-location"></a>Удаление места из местоположения для экстренного помощи

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **адреса** для экстренного  >  **устранения экстренных служб.**
2. В списке щелкните название расположения, из которого вы хотите удалить место.
3. На **вкладке "Места"** выберите место, которое нужно удалить, и нажмите кнопку **"Удалить".**

### <a name="using-powershell"></a>С помощью PowerShell

См. [remove-CsOnlineLisLocation.](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation)
    
## <a name="related-topics"></a>Статьи по теме

- [Добавление, изменение и удаление места для расположения для экстренного реагирования для организации](add-change-remove-emergency-place-organization.md)
- [Управление номерами телефонов организации](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Условия и положения, распространяющиеся на экстренные вызовы](/microsoftteams/emergency-calling-terms-and-conditions)
