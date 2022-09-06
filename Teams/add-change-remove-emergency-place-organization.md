---
title: Добавление, изменение и удаление мест для расположений для экстренного реагирования
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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Узнайте, как добавить, изменить или удалить место для экстренного реагирования в вашей организации.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 37ccf72868819c515a2f7320b112f81f31f65a34
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606718"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>Добавление, изменение и удаление места для расположения для экстренного реагирования для организации

В зависимости от количества физических расположений в организации можно добавить места для  зданий, этажей и офисов, чтобы создать более конкретное местоположение для экстренного реагирования.

Однако в зависимости от варианта подключения к ТСОП способ управления местоположениями для экстренного реагирования и требованиями к расположению может отличаться. Дополнительные сведения см. в разделе ["Управление экстренными звонками"](what-are-emergency-locations-addresses-and-call-routing.md).

В этой статье описывается, как добавить, изменить или удалить место  для экстренного размещения в вашей организации.

Эта статья относится к планам звонков Майкрософт, Operator Connect, Operator Connect Mobile (общедоступная предварительная версия) и прямой маршрутизации.

Вы управляете расположениями для экстренного реагирования для своей организации в Центре администрирования Microsoft Teams или с помощью PowerShell.
  
## <a name="add-a-place-to-an-emergency-location"></a>Добавление места в расположение для экстренного реагирования

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **"Местоположения** > **для экстренного реагирования"**.
2. В списке щелкните имя расположения, для которого вы хотите добавить место.
3. На **вкладке "Места** " нажмите кнопку **"Добавить"**.
4. Введите имя места и нажмите кнопку " **Применить"**.

### <a name="using-powershell"></a>С помощью PowerShell

См [. раздел New-CsOnlineLisLocation](/powershell/module/skype/new-csonlinelislocation).
    
## <a name="change-a-place-for-an-emergency-location"></a>Изменение расположения для экстренного реагирования

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **"Местоположения** > **для экстренного реагирования"**.
2. В списке щелкните имя расположения, для которого нужно изменить место.
3. На **вкладке "** Места" выберите нужное место и нажмите кнопку "Изменить **"**.
4. Обновите сведения о месте и нажмите кнопку " **Применить"**.

### <a name="using-powershell"></a>С помощью PowerShell

См [. раздел Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).
    
## <a name="remove-a-place-from-an-emergency-location"></a>Удаление места из расположения для экстренного реагирования

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **"Местоположения** > **для экстренного реагирования"**.
2. В списке щелкните имя расположения, для которого нужно удалить место.
3. На **вкладке "** Места" выберите нужное место и нажмите кнопку " **Удалить"**.

### <a name="using-powershell"></a>С помощью PowerShell

См [. раздел Remove-CsOnlineLisLocation](/powershell/module/skype/remove-csonlinelislocation).
    
## <a name="related-topics"></a>См. также

- [Управление экстренными звонками](what-are-emergency-locations-addresses-and-call-routing.md)
- [Добавление, изменение и удаление расположения для экстренного реагирования для организации](add-change-remove-emergency-location-organization.md)
- [Управление номерами телефонов для организации](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Условия и положения, распространяющиеся на экстренные вызовы](./emergency-calling-terms-and-conditions.md)