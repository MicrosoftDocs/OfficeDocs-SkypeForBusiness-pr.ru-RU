---
title: Добавление, изменение и удаление местоположений для экстренных случаев
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
description: 'Сведения о том, как добавить, изменить или удалить расположение для экстренного реагирования для вашей организации в центре администрирования Microsoft Teams. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 762246630d245acf92c16aff8df2c9392a307b07
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788573"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Добавление, изменение и удаление местоположения организации для экстренного реагирования

Место для экстренного реагирования должно быть связано с номером телефона, но это может отличаться в зависимости от стран и регионов. Например, в США вы должны ассоциировать место, когда вы назначаете пользователю номер телефона. В Великобритании вы должны связать место с телефонным номером, если вы получаете номера телефонов от Microsoft 365 или Office 365 или переадресовать номера телефонов, предоставленные текущим поставщиком услуг.

Вне зависимости от того, где находится ваша страна или регион, вы можете добавить место или места в место для экстренного реагирования и удалить место для экстренного реагирования. В зависимости от количества физических местоположений в вашей организации вы можете создавать места для зданий, этажей и офисов. Смотрите [Управление вызовом экстренной](what-are-emergency-locations-addresses-and-call-routing.md)помощи.
  
Сведения о том, как получить план звонков и затраты на него, можно найти [в разделе Лицензирование надстроек для Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).

Вы управляете местоположениями для экстренного реагирования для вашей организации в центре администрирования Microsoft Teams или с помощью PowerShell.
  
## <a name="add-an-emergency-location"></a>Добавление места для экстренного реагирования

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации центра администрирования Microsoft Teams **выберите пункты**  >  **адреса для экстренного**реагирования.
2. Нажмите **Добавить**.
3. Введите имя и описание местоположения.
4. Выберите страну или регион, а затем введите адрес.

   > [!NOTE]
   > В Бельгии, Франции, Германии, Ирландии, Нидерланды и Испании важно понимать, что для успешной активации номера телефона в Microsoft 365 или Office 365 адрес, указанный в местоположении для экстренного реагирования, который используется для получения номера, должен совпадать с кодом города номера телефона.

5. Если адрес не найден и вы хотите изменить адрес вручную, включите **параметр изменить адрес вручную**.
6. Нажмите кнопку **Сохранить**.

### <a name="using-powershell"></a>Использование PowerShell

Просмотреть раздел [New-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress).
    
## <a name="change-an-emergency-location"></a>Изменение местоположения для экстренного реагирования

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации центра администрирования Microsoft Teams **выберите пункты**  >  **адреса для экстренного**реагирования.
2. Выберите в списке расположение, которое вы хотите изменить, и нажмите кнопку **изменить**.
3. Внесите нужные изменения.
4. Нажмите кнопку **Сохранить**.

> [!NOTE]
> Сведения об адресе можно изменить только в том случае, если адрес не прошел проверку. Если адрес уже прошел проверку и вам нужно изменить адрес, удалите его, а затем создайте новое расположение с правильным адресом.

### <a name="using-powershell"></a>Использование PowerShell

Смотрите раздел [Set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress).
    
## <a name="remove-an-emergency-location"></a>Удаление местоположения для экстренного реагирования

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации центра администрирования Microsoft Teams **выберите пункты**  >  **адреса для экстренного**реагирования.
2. Выберите в списке место, которое вы хотите удалить, и нажмите кнопку **Удалить**.

### <a name="using-powershell"></a>Использование PowerShell

В разделе [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress).

## <a name="related-topics"></a>Статьи по теме

- [Управление вызовом экстренной помощи](what-are-emergency-locations-addresses-and-call-routing.md)
- [Добавление, изменение и удаление места для расположения для экстренного реагирования для организации](add-change-remove-emergency-place-organization.md)
- [Управление номерами телефонов организации](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Условия и положения, распространяющиеся на экстренные вызовы](/microsoftteams/emergency-calling-terms-and-conditions)
