---
title: Добавление, изменение и удаление расположений для экстренного реагирования
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
description: Сведения о добавлении, изменении или удалении местоположения для экстренного реагирования в организации.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 23eb549592c8ead6983253d1a228020f3851e1a7
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551493"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Добавление, изменение и удаление местоположения организации для экстренного реагирования

Независимо от [варианта подключения по ТСОП](pstn-connectivity.md)&mdash; вы можете связать с номером телефона планы звонков Майкрософт, operator Connect, Teams Phone Mobile или direct Routing&mdash;emergency locations.

Однако в зависимости от варианта подключения к ТСОП способ управления местоположениями для экстренного реагирования и требованиями к расположению может отличаться. Дополнительные сведения см. в разделе ["Управление экстренными звонками"](what-are-emergency-locations-addresses-and-call-routing.md).

В этой статье описывается добавление, изменение или удаление местоположения для экстренного реагирования в вашей организации. 

Эта статья относится к планам звонков Майкрософт, Operator Connect, Teams Phone Mobile и прямой маршрутизации.

Вы управляете расположениями для экстренного реагирования для своей организации в Центре администрирования Microsoft Teams или с помощью PowerShell.

Чтобы назначить местоположение для экстренного реагирования, пользователи, номера телефонов и местоположения для экстренного реагирования должны быть в одной стране. Дополнительные сведения см. в [статье "Назначение или изменение местоположения для экстренного реагирования для пользователя"](assign-change-emergency-location-user.md).
  
## <a name="add-an-emergency-location"></a>Добавление местоположения для экстренного реагирования

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **"Местоположения** > **для экстренного реагирования"**.
2. Нажмите **Добавить**.
3. Введите имя и описание расположения.
4. Выберите страну или регион, а затем введите адрес.

   > [!NOTE]
   > В Бельгии, Франции, Германии, Ирландии, Нидерландов и Испании важно понимать, что для успешной активации номера телефона в Microsoft 365 адрес, который настроен в расположении для экстренного реагирования, который используется для получения номера, должен соответствовать коду области номера телефона.

5. Если адрес не найден и вы хотите изменить адрес вручную, включите параметр **"Изменить адрес" вручную**.
6. Нажмите кнопку **Сохранить**.

### <a name="using-powershell"></a>С помощью PowerShell

См [. раздел New-CsOnlineLisCivicAddress](/powershell/module/skype/new-csonlineliscivicaddress).
    
## <a name="change-an-emergency-location"></a>Изменение местоположения для экстренного реагирования

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **"Местоположения** > **для экстренного реагирования"**.
2. В списке выберите расположение, которое нужно изменить, и нажмите кнопку "Изменить **"**.
3. Внесите необходимые изменения.
4. Нажмите кнопку **Сохранить**.

> [!NOTE]
> Сведения об адресе для расположения можно изменить только в том случае, если адрес не проверен. Если адрес уже проверен и необходимо изменить адрес, удалите расположение, а затем создайте новое расположение с правильным адресом.

### <a name="using-powershell"></a>С помощью PowerShell

См [. раздел Set-CsOnlineLisCivicAddress](/powershell/module/skype/set-csonlineliscivicaddress).
    
## <a name="remove-an-emergency-location"></a>Удаление местоположения для экстренного реагирования

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **"Местоположения** > **для экстренного реагирования"**.
2. В списке выберите расположение, которое нужно удалить, и нажмите кнопку **"Удалить"**.

### <a name="using-powershell"></a>С помощью PowerShell

См [. раздел Remove-CsOnlineLisCivicAddress](/powershell/module/skype/remove-csonlineliscivicaddress).

## <a name="related-topics"></a>См. также

- [Управление экстренными звонками](what-are-emergency-locations-addresses-and-call-routing.md)
- [Добавление, изменение и удаление места для расположения для экстренного реагирования для организации](add-change-remove-emergency-place-organization.md)
- [Управление номерами телефонов для организации](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Условия и положения, распространяющиеся на экстренные вызовы](./emergency-calling-terms-and-conditions.md)