---
title: Добавление, изменение и удаление местоположений для экстренного устранения
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
description: 'Узнайте, как добавлять, изменять и удалять местоположения для экстренного устранения экстренных ситуаций в организации. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4d9c7c56b4e2b2fd14f703d51b4c07cfc173dfa3
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634858"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Добавление, изменение и удаление местоположения организации для экстренного реагирования

Независимо от [варианта подключения к ПСОП](pstn-connectivity.md) вы можете выбрать планы звонков Майкрософт, операторы Подключение или прямые маршруты для экстренного вызова могут быть связаны с &mdash; &mdash; телефонным номером.

Тем не менее, в зависимости от варианта подключения к ДНР способ управления местоположениями для экстренного экстренного ситуация и требования к местоположению могут различаться. Дополнительные сведения см. в [управлении экстренных вызовов.](what-are-emergency-locations-addresses-and-call-routing.md)

В этой статье описано, как добавлять, изменять и удалять местоположения для экстренного устранения экстренных ситуаций в организации. 

Эта статья относится к планам звонков Майкрософт, Подключение и прямой маршрутике.

Вы управляете местоположениями для экстренного экстренного ситуация в Microsoft Teams центре администрирования или с помощью PowerShell.

Чтобы назначить местоположение для экстренного ситуация, все пользователи, номера телефонов и местоположения для экстренного экстренного ситуация должны быть в одной стране. Дополнительные сведения см. в статьи Назначение или изменение местоположения для экстренного [ситуация для пользователя.](assign-change-emergency-location-user.md)
  
## <a name="add-an-emergency-location"></a>Добавление местоположения для экстренного ситуация

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **Адреса** для экстренного  >  **устранения чрезвычайной ситуации**.
2. Нажмите **Добавить**.
3. Введите имя и описание расположения.
4. Выберите страну или регион и введите адрес.

   > [!NOTE]
   > В Бельгии, Франции, Германии, Ирландии, Нидерланды и Испании важно понимать, что для успешной активации телефонного номера в Microsoft 365 адрес, за используемый для получения номера, должен соответствовать коду города.

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
2. В списке выберите расположение, которое вы хотите удалить, и нажмите кнопку **Удалить**.

### <a name="using-powershell"></a>С помощью PowerShell

См. [remove-CsOnlineLisCivicAddress](/powershell/module/skype/remove-csonlineliscivicaddress).

## <a name="related-topics"></a>Статьи по теме

- [Управление звонками экстренных служб](what-are-emergency-locations-addresses-and-call-routing.md)
- [Добавление, изменение и удаление места для расположения для экстренного реагирования для организации](add-change-remove-emergency-place-organization.md)
- [Управление номерами телефонов организации](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Условия и положения, распространяющиеся на экстренные вызовы](./emergency-calling-terms-and-conditions.md)