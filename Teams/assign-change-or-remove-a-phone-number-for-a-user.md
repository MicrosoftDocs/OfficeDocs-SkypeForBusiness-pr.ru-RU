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
description: Узнайте, как назначить, изменить или удалить рабочий номер телефона для Teams, чтобы внешние компании и клиенты могли звонить.
ms.openlocfilehash: 443fdb5833e657c3f45c0f53d1d4ce6744bd67b0b83247e72084e3d29f6c1bc7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320032"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user-calling-plans"></a>Назначение, изменение и удаление номера телефона пользователя (планы звонков)

При настройках планов звонков пользователям назначаются номера телефонов. В Microsoft Teams при нажатии кнопки Звонки будет указан номер телефона, который вы **назначаете.** Инструкции по назначению, изменению и удалению номера телефона пользователя в сценарии [](./direct-routing-enable-users.md)прямой маршрутии см. в этой ссылке.

![Номер телефона пользователя, отображаемого в Teams.](media/teams-phone-number.png)

При настройке пользователей таким образом, чтобы они могли звонить и принимать телефонные звонки, необходимо сначала использовать центр администрирования Microsoft Teams и назначить номер телефона. При необходимости вы можете изменить или удалить номер телефона.
  
Чтобы узнать, как получить планы звонков в Teams и сколько они стоят, см. Teams лицензирования [надстройки](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
  
> [!NOTE]
> Чтобы узнать, назначена ли пользователю лицензия, переходить в центр администрирования Microsoft Teams и > **пользователей.** Если лицензия назначена, она будет указана на странице.  Вы также можете использовать Центр администрирования Microsoft 365.
  
## <a name="assign-a-phone-number-to-a-user"></a>Назначение номера телефона пользователю
 
![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**
    
1. В области навигации слева щелкните **Голосовая**  >  **Телефон номера**.
2. На странице **Телефон номеров** выберите в списке ненаученный номер и нажмите кнопку **Изменить**.  
3. В области **правки** в **области** Назначено найдите пользователя по отображаемом имени или имени пользователя, а затем нажмите кнопку **Назначить**.
4. Чтобы назначить или изменить связанное местоположение для экстренного ситуация, в области Местоположение для экстренного **ситуация** найди и выберите нужное расположение.
5. В зависимости от того, хотите ли вы отправить пользователю сообщение электронной почты со сведениями о телефонном номере, отключите или включите отправку электронной почты пользователю со сведениями о **телефонном номере**. По умолчанию этот режим в том же режиме. 
6. Нажмите кнопку **Сохранить**.

Пример PowerShell см. [в примере Set-CsOnlineVoiceUser.](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

    > [!NOTE]
    > Because of the latency between Microsoft 365 or Office 365 and Teams, it can take up to 24 hours for users to be enabled. If the phone number isn't assigned correctly after 24 hours, [contact support for business products - Admin Help](/microsoft-365/admin/contact-support-for-business-products). We're here to help!

  
## <a name="change-a-phone-number-for-a-user"></a>Изменение номера телефона пользователя
 
![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**
    
1. В левой области навигации щелкните Пользователи **,** найдите и дважды щелкните нужного пользователя, щелкните Учетная запись **,** а затем в области Общие сведения заметьте номер телефона, который назначен пользователю.
2. В области навигации слева щелкните **Голосовая**  >  **Телефон номера**.
3. На странице **Телефон номера** выберите номер, который вы определили в шаге 1, и нажмите кнопку **Изменить**.  
4. В области **правки** в области **Назначено** щелкните **X,** чтобы удалить пользователя.
5. Нажмите кнопку **Сохранить**.
6. На странице **Телефон номеров** выберите в списке ненаученный номер и нажмите кнопку **Изменить**.  
7. В области **правки** в **области** Назначено найдите пользователя по отображаемом имени или имени пользователя, а затем нажмите кнопку **Назначить**.
8. Чтобы назначить или изменить связанное местоположение для экстренного ситуация, в области Местоположение для экстренного **ситуация** найди и выберите нужное расположение.
9. Нажмите кнопку **Сохранить**.

Пример PowerShell см. в [примере Set-CsOnlineVoiceUser.](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

## <a name="remove-a-phone-number-from-a-user"></a>Удаление номера телефона пользователя
 
![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**

1. В левой области навигации щелкните Пользователи **,** найдите и дважды щелкните нужного пользователя, щелкните Учетная запись **,** а затем в области Общие сведения заметьте номер телефона, который назначен пользователю.
2. В области навигации слева щелкните **Голосовая**  >  **Телефон номера**.
3. На странице **Телефон номера** выберите номер, который вы определили в шаге 2, и нажмите кнопку **Изменить**.  
4. В области **правки** в области **Назначено** щелкните **X,** чтобы удалить пользователя.
5. Нажмите кнопку **Сохранить**.

Пример PowerShell см. в [примере Set-CsOnlineVoiceUser.](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

## <a name="related-topics"></a>Статьи по теме

[Что такое проверка адреса?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Управление номерами телефонов организации](/microsoftteams/manage-phone-numbers-for-your-organization)

[Условия и положения, распространяющиеся на экстренные вызовы](./emergency-calling-terms-and-conditions.md)

[Отказ от ответственности для экстренных вызовов](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

[Планы звонков для Microsoft 365](./calling-plans-for-office-365.md)