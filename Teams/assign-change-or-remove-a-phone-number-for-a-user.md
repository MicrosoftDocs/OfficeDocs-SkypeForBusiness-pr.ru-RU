---
title: Назначение, изменение и удаление номера телефона пользователя
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Узнайте, как назначить, изменить или удалить рабочий номер телефона для пользователей Teams, чтобы внешние организации и клиенты могли звонить.
ms.openlocfilehash: e606885aee1e87dfdfc9b36a5247eedba225a185
ms.sourcegitcommit: 91fbc7c9cd43c2a5b7e6dfedf2388939f2f77d57
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2021
ms.locfileid: "50589623"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user-calling-plans"></a>Назначение, изменение или удаление номера телефона пользователя (планы звонков)

При назначении планов звонков пользователям назначаются телефонные номера. В Microsoft Teams номер телефона, который вы назначаете, указан при нажатии кнопки **"Звонки".** Инструкции по назначению, изменению и удалению номера телефона пользователя в сценарии [](https://docs.microsoft.com/microsoftteams/direct-routing-enable-users)прямой маршрутки см. в инструкциях по прямой маршрутике, голосовой и голосовой почте.

![Номер телефона пользователя, отображаемого в Teams.](media/teams-phone-number.png)

При настройке пользователей для того, чтобы они могли звонить и принимать телефонные звонки, необходимо сначала использовать Центр администрирования Microsoft Teams и назначить номер телефона. При необходимости вы можете изменить или удалить номер телефона.
  
Чтобы узнать, как получить планы звонков в Teams и сколько они стоят, см. лицензирование [надстройки Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
  
> [!NOTE]
> Чтобы узнать, назначена ли пользователю лицензия, переходить в Центр администрирования Microsoft Teams > **Users.** Если лицензия назначена, она будет указана на странице.  Вы также можете использовать Центр администрирования Microsoft 365.
  
## <a name="assign-a-phone-number-to-a-user"></a>Назначение номера телефона пользователю
 
![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**
    
1. В области навигации слева щелкните **"Номера**  >  **голосовых телефонов".**
2. На странице **"Номера телефонов"** выберите в списке ненаписаный номер и нажмите кнопку "Изменить".   
3. В области **редактирования** в области "Назначено" найдите пользователя по отображаемом имени или имени пользователя, а затем нажмите кнопку "Назначить". 
4. Чтобы назначить или изменить связанное местоположение для экстренного помощи, в области **"Местоположение для** экстренного помощи" наберите и выберите нужное расположение.
5. В зависимости от того, хотите ли вы отправить пользователю сообщение электронной почты со сведениями о номере телефона, отключите или включите для пользователя электронной почты сведения о **телефонном номере.** По умолчанию этот режим имеет значение "В этом режиме". 
6. Щелкните **Сохранить**.

Пример PowerShell см. в [примере Set-CsOnlineVoiceUser.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

    > [!NOTE]
    > Because of the latency between Microsoft 365 or Office 365 and Teams, it can take up to 24 hours for users to be enabled. If the phone number isn't assigned correctly after 24 hours, [contact support for business products - Admin Help](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products). We're here to help!

  
## <a name="change-a-phone-number-for-a-user"></a>Изменение номера телефона пользователя
 
![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**
    
1. В области навигации слева выберите "Пользователи", найдите и дважды щелкните нужного пользователя, щелкните "Учетная запись", а затем в области "Общие сведения" обратите внимание на номер телефона, который назначен пользователю. 
2. В области навигации слева щелкните **"Номера**  >  **голосовых телефонов".**
3. На странице **"Номера телефонов"** выберите номер, который вы определили в шаге 1, и нажмите кнопку "Изменить".   
4. В области **редактирования** в **области**"Назначено" щелкните **X,** чтобы удалить пользователя.
5. Щелкните **Сохранить**.
6. На странице **"Номера телефонов"** выберите в списке ненаписаный номер и нажмите кнопку "Изменить".   
7. В области **редактирования** в области "Назначено" найдите пользователя по отображаемом имени или имени пользователя, а затем нажмите кнопку "Назначить". 
8. Чтобы назначить или изменить связанное местоположение для экстренного помощи, в области **"Местоположение для** экстренного помощи" наберите и выберите нужное расположение.
9. Щелкните **Сохранить**.

Пример PowerShell см. в [примере Set-CsOnlineVoiceUser.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

## <a name="remove-a-phone-number-from-a-user"></a>Удаление номера телефона пользователя
 
![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**

1. В области навигации слева выберите "Пользователи", найдите и дважды щелкните нужного пользователя, щелкните "Учетная запись", а затем в области "Общие сведения" обратите внимание на номер телефона, который назначен пользователю. 
2. В области навигации слева щелкните **"Номера**  >  **голосовых телефонов".**
3. На странице **"Номера телефонов"** выберите номер, который вы определили в шаге 2, и нажмите кнопку "Изменить".   
4. В области **редактирования** в **области**"Назначено" щелкните **X,** чтобы удалить пользователя.
5. Щелкните **Сохранить**.

Пример PowerShell см. в [примере Set-CsOnlineVoiceUser.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

## <a name="related-topics"></a>Статьи по теме

[Что такое проверка адреса?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Управление номерами телефонов организации](/microsoftteams/manage-phone-numbers-for-your-organization)

[Условия и положения, распространяющиеся на экстренные вызовы](/microsoftteams/emergency-calling-terms-and-conditions)

[Метка заявление об отказе для экстренных вызовов](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

[Планы звонков для Microsoft 365](https://docs.microsoft.com/MicrosoftTeams/calling-plans-for-office-365)
