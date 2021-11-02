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
description: Узнайте, как добавить, изменить или удалить место для экстренного размещения в организации.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fec188634377b04cb4149d3680acc07eef797149
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634878"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>Добавление, изменение и удаление места для расположения для экстренного реагирования для организации

В зависимости от количества физических расположений  в организации вы можете добавить места для зданий, этажей и офисов, чтобы создать более конкретное местоположение для экстренного нахождения.

Однако в зависимости от варианта подключения к ДНР способ управления местоположениями для экстренного ситуация и требования к местоположению могут различаться. Дополнительные сведения см. в [управлении экстренных вызовов.](what-are-emergency-locations-addresses-and-call-routing.md)

В этой статье описано, как добавить, изменить или удалить место для экстренного размещения в организации. 

Эта статья относится к планам звонков Майкрософт, Подключение и прямой маршрутике.

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

- [Управление звонками экстренных служб](what-are-emergency-locations-addresses-and-call-routing.md)
- [Добавление, изменение и удаление расположения для экстренного реагирования для организации](add-change-remove-emergency-location-organization.md)
- [Управление номерами телефонов организации](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Условия и положения, распространяющиеся на экстренные вызовы](./emergency-calling-terms-and-conditions.md)