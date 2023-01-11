---
title: Добавление, изменение, удаление расположений для экстренного реагирования
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
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Узнайте, как добавить, изменить или удалить расположение для экстренного реагирования в организации.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 99ab0821b8ccdb14664dc0a2aa37c959499ff8ac
ms.sourcegitcommit: 66d8e3d7a29a03c5deba9780964bc03f6587017f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2023
ms.locfileid: "69774744"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Добавление, изменение и удаление местоположения организации для экстренного реагирования

Независимо от [варианта подключения к ТСОП](pstn-connectivity.md) вы выбираете&mdash;Планы звонков Майкрософт, Оператор Connect, Teams Phone Mobile или Прямая маршрутизация расположения для экстренного реагирования&mdash;могут быть связаны с номером телефона.

Однако в зависимости от варианта подключения ТСОП управление расположениями для экстренного реагирования и требования к расположению могут отличаться. Дополнительные сведения см. в разделе [Управление экстренными вызовами](what-are-emergency-locations-addresses-and-call-routing.md).

В этой статье описывается, как добавить, изменить или удалить расположение для экстренного реагирования для организации. 

Эта статья относится к тарифным планам Майкрософт, Оператору Connect, Мобильному телефону Teams и Прямой маршрутизации.

Вы управляете расположениями для экстренного реагирования для своей организации в Центре администрирования Microsoft Teams или с помощью PowerShell.

Чтобы назначить место для экстренного реагирования, пользователи, номера телефонов и места для экстренного реагирования должны находиться в одной стране. Дополнительные сведения см. в статье [Назначение или изменение расположения для экстренного реагирования для пользователя](assign-change-emergency-location-user.md).
  
## <a name="add-an-emergency-location"></a>Добавление расположения для экстренного реагирования

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **Расположения** > **Адреса для экстренной помощи**.
2. Нажмите **Добавить**.
3. Введите имя и описание расположения.
4. Выберите страну или регион, а затем введите адрес.

   > [!NOTE]
   > В Бельгии, Франции, Германии, Ирландии, Нидерландах и Испании важно понимать, что для успешной активации номера телефона в Microsoft 365 адрес, настроенный в месте экстренного реагирования, который используется для получения номера, должен соответствовать коду номера телефона.

5. Если адрес не найден и вы хотите вручную изменить адрес, включите **параметр Изменить адрес вручную**.
6. Нажмите кнопку **Сохранить**.

### <a name="using-powershell"></a>С помощью PowerShell

См [. раздел New-CsOnlineLisCivicAddress](/powershell/module/skype/new-csonlineliscivicaddress).
    
## <a name="change-an-emergency-location"></a>Изменение местоположения для экстренного реагирования

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **Расположения** > **Адреса для экстренной помощи**.
2. В списке выберите расположение, которое нужно изменить, и нажмите кнопку **Изменить**.
3. Внесите нужные изменения.
4. Нажмите кнопку **Сохранить**.

> [!NOTE]
> Изменить сведения об адресе для расположения можно только в том случае, если адрес не проверен. Если адрес уже проверен и необходимо изменить адрес, удалите расположение, а затем создайте новое расположение с правильным адресом.

### <a name="using-powershell"></a>С помощью PowerShell

См [. раздел Set-CsOnlineLisCivicAddress](/powershell/module/skype/set-csonlineliscivicaddress).
    
## <a name="remove-an-emergency-location"></a>Удаление расположения для экстренного реагирования

> [!NOTE]
> Удалить расположение можно только в том случае, если ему не назначены пользователи или номера телефонов. Если в расположении назначены номера или пользователи, сначала их необходимо удалить.

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **Расположения** > **Адреса для экстренной помощи**.
2. В списке выберите расположение, которое нужно удалить, и нажмите кнопку **Удалить**.

### <a name="using-powershell"></a>С помощью PowerShell

См [. раздел Remove-CsOnlineLisCivicAddress](/powershell/module/skype/remove-csonlineliscivicaddress).

## <a name="related-topics"></a>См. также

- [Управление экстренными вызовами](what-are-emergency-locations-addresses-and-call-routing.md)
- [Добавление, изменение и удаление места для расположения для экстренного реагирования для организации](add-change-remove-emergency-place-organization.md)
- [Управление номерами телефонов для организации](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Условия и положения, распространяющиеся на экстренные вызовы](./emergency-calling-terms-and-conditions.md)
