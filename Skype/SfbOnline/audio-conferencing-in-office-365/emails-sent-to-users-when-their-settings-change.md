---
title: Сообщения электронной почты, отправленные пользователям при изменении их параметров в Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Узнайте, какие сведения автоматически отправляются пользователям по электронной почте при изменении параметров Skype для бизнеса Online. '
ms.openlocfilehash: cb456b9345d8dce1aa7a1d619371f8a2f65eab36
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011953"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a>Сообщения электронной почты, отправленные пользователям при изменении их параметров в Skype для бизнеса Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Если вы ищете автоматическую отправку данных электронной почты в Microsoft Teams, см. электронные письма, отправленные пользователям при изменении их параметров [в Microsoft Teams.](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams)

Сообщения электронной почты автоматически отправляются пользователям, у которых включена аудиоконференция с использованием Майкрософт в качестве поставщика услуг аудиоконференций. [](set-up-audio-conferencing.md)
  
По умолчанию пользователям, для которых включена аудиоконференция, отправляются четыре типа электронной почты. Однако если вы хотите ограничить количество сообщений, отправленных пользователям, вы можете отключить их. Аудиоконференция в Microsoft 365 или Office 365 отправляет сообщения электронной почты пользователям в:
  
- **Им назначена лицензия на аудиоконференцию или при смене поставщика аудиоконференций на Майкрософт.**
    
     Это сообщение электронной почты содержит код конференции, номер телефона конференции по умолчанию для собраний, ПИН-код аудиоконференции для пользователя, а также инструкции и ссылку для использования средства обновления собраний по сети Skype для бизнеса, которое используется для обновления существующих собраний для пользователя. См. [Skype для бизнеса лицензий на](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) аудиоконференцию или Назначение Майкрософт в качестве поставщика [аудиоконференций.](assign-microsoft-as-the-audio-conferencing-provider.md)
    
    > [!NOTE]
    > Если в вашей организации включены динамические ИД конференции, все собрания пользователя, которые он запланет, будут иметь уникальные ИД конференции. Вы можете настроить [динамические ID](./reset-a-conference-id-for-a-user.md)аудиоконференции в своей организации. 
  
    Вот пример такого сообщения:
    
     ![Skype для бизнеса Проверить лицензию.](../images/audio-conferencing-user-enabled.png)
  
    Дополнительные информацию о лицензировании Skype для бизнеса дополнительных лицензий можно найти в Skype для бизнеса [надстройки](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
- **Изменяется ИД конференции или телефонный номер конференции по умолчанию пользователя.**
    
    Это сообщение электронной почты содержит номер конференции, номер телефона конференции по умолчанию, а также инструкции и ссылку для использования средства обновления собраний по сети Skype для бизнеса, которое используется для обновления существующих собраний для пользователя. Но это сообщение электронной почты не содержит ПИН-код аудиоконференции пользователя. See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).
    
    > [!NOTE]
    > Если в вашей организации включены динамические ИД конференции, все собрания пользователя, которые он запланет, будут иметь уникальные ИД конференции. Вы можете настроить [динамические ID](./reset-a-conference-id-for-a-user.md)аудиоконференции в своей организации. 
  
    Вот пример такого сообщения:
    
     ![Сведения о телефонном подмене изменены.](../images/audio-conferencing-info-change.png)
  
- **Пин-код аудиоконференции пользователя сбрасывается.**
    
    Это сообщение электронной почты содержит ПИН-код аудиоконференции организатора, существующий код конференции и телефонный номер конференции по умолчанию для пользователя. См. [сброс ПИН-кода аудиоконференции.](reset-the-audio-conferencing-pin.md)
    
    > [!NOTE]
    > Если в вашей организации включены динамические ИД конференции, все собрания пользователя, которые он запланет, будут иметь уникальные ИД конференции. Вы можете настроить [динамические ID](./reset-a-conference-id-for-a-user.md)аудиоконференции в своей организации. 
  
    Вот пример такого сообщения:
    
     ![Изменен ПИН-код для телефонной телефонной телефонии.](../images/audio-conferencing-pin-has-changed.png)
  
- **Лицензия пользователя удаляется либо поставщик аудиоконферент изменяется с Майкрософт на другого поставщика или нет.**
    
    Это происходит  при удалении лицензии пользователя на аудиоконференцию или при смене поставщика услуг аудиоконференций с Майкрософт на стороного поставщика аудиоконференций или при установке для него параметра **Нет.** Это сообщение электронной почты содержит инструкции и сведения для пользователя по использованию средства обновления собраний Skype для бизнеса по сети для удаления определенных сведений о аудиоконференции, таких как номер конференции по умолчанию или номер конференции.
    
    См. [назначение и удаление лицензий для Приложения Microsoft 365 для бизнеса.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)
    
    Вот пример такого сообщения:
    
     ![Conferencing dial-in conferencing is turned off.](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Внесение изменений в отправленные им сообщения электронной почты

Вы можете внести изменения в сообщение электронной почты, которое автоматически отправляется пользователям, включая адрес электронной почты и отображаемую фамилию, которая содержится в *контактных* данных "От". По умолчанию отправитель сообщений отправляется из Microsoft 365 или Office 365, но вы можете изменить адрес электронной почты и отображаемого имени с помощью Windows PowerShell и с помощью Windows PowerShell [Set-CsOnlineDialInConferencingTenantSettings.](/previous-versions//mt228132(v=technet.10)) Чтобы изменить адрес электронной почты, отправляемый пользователям, необходимо:
  
- Введите адрес электронной почты в параметр  _SendEmailFromAddress_.
    
- Введите отображаемое имя в параметр  _SendEmailFromDisplayName_.
    
- Задайте  _для параметра SendEmailOverride_ параметр  _True_.
    
Вы можете внести изменения в сообщения электронной почты, отправленные пользователям, например адрес электронной почты, с которого было отправлено сообщение, и отображаемую его имя, вы можете:
  
```PowerShell
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  Если вы хотите изменить сведения об адресе электронной почты, убедитесь, что политики входящие электронной почты в вашей среде позволяют отправлять сообщения, отправленные с настраиваемого адреса. При переопределения контактных данных *"От"* убедитесь, что сообщения правильно отправлены пользователям. Вы можете сделать это, опробуя это с одним пользователем в организации.
  
Для управления другими настройками организации, включая электронную почту, можно использовать [set-CsOnlineDialInConferencingTenantSettings.](/previous-versions//mt228132(v=technet.10))
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>Что делать, если вы не хотите, чтобы им отправляли электронную почту?

Если отключить отправку сообщений пользователям, они не будут отправляться даже при назначении пользователю лицензии. В этом случае код конференции, номер телефона для конференц-связи по умолчанию и, что важнее, ПИН-код аудиоконференции не будут отправлены пользователю. В этом случае вы должны сообщить пользователю, отправив ему отдельное сообщение электронной почты или позвонив ему.
  
По умолчанию пользователям отправляются сообщения электронной почты, но если вы хотите запретить им получать электронную почту для аудиоконференций, вы можете использовать центр администрирования Skype для бизнеса или Windows PowerShell. 
 
![Значок с логотипом Skype для бизнеса логотипом.](../images/sfb-logo-30x30.png)  **Использование центра Skype для бизнеса администрирования**
    
1. В центре **администрирования** Skype для бизнеса навигации слева перейдите в параметры моста Аудиоконференция  >  **Майкрософт**.
    
2. На странице **параметров моста Microsoft** выберите или отключайте параметр Автоматически отправлять электронные письма пользователям при изменении параметров аудиоконференции.  
    
3. Нажмите кнопку **Сохранить**. 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
**Использование Windows PowerShell**
  
1. Чтобы отключить отправку электронной почты всем пользователям, запустите следующую:
    
   ```PowerShell
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

Для управления другими настройками организации, включая электронную почту, можно использовать [set-CsOnlineDialInConferencingTenantSettings.](/previous-versions//mt228132(v=technet.10))
  
## <a name="what-else-should-you-know-about-this-email"></a>Что еще необходимо знать о таких сообщениях?

- Дополнительные параметры включения и отключения автоматической отправки электронной почты пользователям см. в записи Включение и отключение отправки сообщений электронной почты при изменении параметров [аудиоконференции.](enable-or-disable-sending-emails-when-their-settings-change.md)
    
- Иногда пользователи теряют свои звуковые данные, и вам необходимо иметь возможность отправить им всю информацию о звуке. Для этого в Центре администрирования Skype для бизнеса щелкните  Отправить сведения о конференции по электронной почте в свойствах аудиоконференции для пользователя. See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md). Однако эти сведения не включают ПИН-код аудиоконференции.
    
    Вот пример такого письма, которое будет отправлено:
    
     ![Сообщение электронной почты для телефонной телефонии.](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- По умолчанию отправитель сообщений отправляется из Microsoft 365 или Office 365, но вы можете изменить адрес электронной почты и отображаемого имени с помощью Windows PowerShell и с помощью Windows PowerShell [Set-CsOnlineDialInConferencingTenantSettings.](/previous-versions//mt228132(v=technet.10))
    
- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единого администрирования, который упростит выполнение повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Зачем нужна Microsoft 365 или Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центр администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах: 
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-битных компьютерах, можно скачать из Центра загрузки Майкрософт по ссылке [Загрузка и установка модуля Teams PowerShell][HELP](../set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md)(/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector).
  
## <a name="related-topics"></a>См. также

[Включение и отключение отправки писем при смене настроек аудиоконференций](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции](send-an-email-to-a-user-with-their-dial-in-information.md)
