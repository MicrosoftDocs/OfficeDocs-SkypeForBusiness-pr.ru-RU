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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: 'Узнайте, как добавить, изменить или удалить местоположение для экстренного устранения чрезвычайной ситуации для организации в центре Microsoft Teams администрирования. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 62604fc26f91baa77bd205869bbe4251d1a46a8a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602304"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Добавление, изменение и удаление местоположения организации для экстренного реагирования

Местоположение для экстренного ситуация должно быть связано с номером телефона, но время его действия может различаться в зависимости от страны и региона. Например, в США при назначении пользователю телефонного номера необходимо связать местоположение для экстренного ситуация. Если вы получаете телефонные номера из Microsoft 365 или Office 365 или переносите телефонные номера от текущего поставщика услуг, вам необходимо связать местоположение для экстренного звонков в Великобритании.

Независимо от страны или региона вы можете добавить место или место для экстренного устранения экстренных ситуаций и удалить его. В зависимости от количества физических мест в организации можно создавать места для зданий, этажей и офисов. См. [управление звонками на экстренные вызовы.](what-are-emergency-locations-addresses-and-call-routing.md)
  
Чтобы узнать, как получить план звонков и сколько они стоят, см. Teams лицензирования [надстройки](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

Вы управляете местоположениями для экстренного ситуация для своей организации в Microsoft Teams центре администрирования или с помощью PowerShell.
  
## <a name="add-an-emergency-location"></a>Добавление местоположения для экстренного ситуация

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **Адреса** для экстренного  >  **устранения чрезвычайной ситуации**.
2. Нажмите **Добавить**.
3. Введите имя и описание расположения.
4. Выберите страну или регион и введите адрес.

   > [!NOTE]
   > В Бельгии, Франции, Германии, Ирландии, Нидерланды и Испании важно понимать, что для успешной активации телефонного номера в Microsoft 365 или Office 365 адрес, за используемый для получения номера, должен соответствовать коду города.

5. Если адрес не найден и вы хотите изменить его вручную, включите изменить адрес **вручную.**
6. Нажмите кнопку **Сохранить**.

### <a name="using-powershell"></a>С помощью PowerShell

См. [раздел New-CsOnlineLisCivicAddress](/powershell/module/skype/new-csonlineliscivicaddress).
    
## <a name="change-an-emergency-location"></a>Изменение местоположения для экстренного реагирования

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **Адреса** для экстренного  >  **устранения чрезвычайной ситуации**.
2. В списке выберите расположение, которое вы хотите изменить, и нажмите кнопку **Изменить**.
3. Внести нужные изменения.
4. Нажмите кнопку **Сохранить**.

> [!NOTE]
> Изменить адрес расположения можно только в том случае, если адрес не проверен. Если адрес уже проверен и вам нужно изменить его, удалите расположение, а затем создайте новое расположение с правильным адресом.

### <a name="using-powershell"></a>С помощью PowerShell

См. [раздел Set-CsOnlineLisCivicAddress](/powershell/module/skype/set-csonlineliscivicaddress).
    
## <a name="remove-an-emergency-location"></a>Удаление местоположения для экстренного устранения

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **Адреса** для экстренного  >  **устранения чрезвычайной ситуации**.
2. Выберите в списке расположение, которое нужно удалить, и нажмите кнопку **Удалить.**

### <a name="using-powershell"></a>С помощью PowerShell

См. [remove-CsOnlineLisCivicAddress](/powershell/module/skype/remove-csonlineliscivicaddress).

## <a name="related-topics"></a>Статьи по теме

- [Управление звонками в экстренные службы](what-are-emergency-locations-addresses-and-call-routing.md)
- [Добавление, изменение и удаление места для расположения для экстренного реагирования для организации](add-change-remove-emergency-place-organization.md)
- [Управление номерами телефонов организации](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Условия и положения, распространяющиеся на экстренные вызовы](./emergency-calling-terms-and-conditions.md)