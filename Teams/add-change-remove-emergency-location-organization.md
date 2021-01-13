---
title: Добавление, изменение и удаление местоположений для экстренного устранения
author: cichur
ms.author: v-cichur
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
description: 'Узнайте, как добавить, изменить или удалить расположение для экстренного устранения экстренных служб для вашей организации в Центре администрирования Microsoft Teams. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a470a75d367bc47d4063a2a99171a4a09e052fca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799949"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Добавление, изменение и удаление местоположения организации для экстренного реагирования

С номером телефона должно быть связано местоположение для экстренного помощи, но время может различаться в зависимости от страны и региона. Например, в США при назначении пользователю телефонного номера необходимо связать местоположение для экстренного помощи. Если вы хотите получить телефонные номера в Microsoft 365 или Office 365 или перенести их у текущего поставщика услуг, вам потребуется связать местоположение для экстренного помощи с номером телефона в Великобритании.

Независимо от страны и региона вы можете добавить место или место в местоположение для экстренного помощи и удалить его. В зависимости от числа физических мест в организации можно создавать расположения для зданий, этажей и офисов. См. [управление экстренным вызовом.](what-are-emergency-locations-addresses-and-call-routing.md)
  
Чтобы узнать, как получить план звонков и сколько они стоят, см. лицензирование [надстройки Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)

Вы управляете местоположениями в организации в Центре администрирования Microsoft Teams или с помощью PowerShell.
  
## <a name="add-an-emergency-location"></a>Добавление местоположения для экстренного помощи

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **адреса** для экстренного  >  **устранения экстренных служб.**
2. Нажмите **Добавить**.
3. Введите имя и описание расположения.
4. Выберите страну или регион и введите адрес.

   > [!NOTE]
   > В Бельгии, Франции, Германии, Ирландии, Нидерландах и Испании важно понимать, что для успешной активации номера телефона в Microsoft 365 или Office 365 адрес, за используемый для получения номера, должен соответствовать коду города.

5. Если адрес не найден и вы хотите изменить его вручную, включите редактирование **адреса вручную.**
6. Щелкните **Сохранить**.

### <a name="using-powershell"></a>С помощью PowerShell

См. [new-CsOnlineLisCivicAddress.](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress)
    
## <a name="change-an-emergency-location"></a>Изменение местоположения для экстренного реагирования

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **адреса** для экстренного  >  **устранения экстренных служб.**
2. В списке выберите расположение, которое вы хотите изменить, и нажмите кнопку **"Изменить".**
3. Внести нужные изменения.
4. Щелкните **Сохранить**.

> [!NOTE]
> Вы можете изменить адрес расположения, только если адрес не проверен. Если адрес уже проверен и вам нужно изменить его, удалите расположение, а затем создайте новое расположение с правильным адресом.

### <a name="using-powershell"></a>С помощью PowerShell

См. [set-CsOnlineLisCivicAddress.](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress)
    
## <a name="remove-an-emergency-location"></a>Удаление местоположения для экстренного устранения

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **адреса** для экстренного  >  **устранения экстренных служб.**
2. В списке выберите расположение, которое вы хотите удалить, и нажмите кнопку **"Удалить".**

### <a name="using-powershell"></a>С помощью PowerShell

См. [remove-CsOnlineLisCivicAddress.](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress)

## <a name="related-topics"></a>Статьи по теме

- [Управление экстренным вызовом](what-are-emergency-locations-addresses-and-call-routing.md)
- [Добавление, изменение и удаление места для расположения для экстренного реагирования для организации](add-change-remove-emergency-place-organization.md)
- [Управление номерами телефонов организации](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Условия и положения, распространяющиеся на экстренные вызовы](/microsoftteams/emergency-calling-terms-and-conditions)
