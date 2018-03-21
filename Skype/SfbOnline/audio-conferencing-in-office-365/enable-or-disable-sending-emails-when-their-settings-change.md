---
title: "Включение и отключение отправки по электронной почте при изменении их параметров"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 3fd5d7c5f12b3e5a88a217eae9a0a86ab0ea9720
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2018
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a>Включение и отключение отправки сообщения электронной почты при изменении параметров аудиоконференций

Пользователи автоматически уведомления по электронной почте, включенный для аудиоконференции. Возможны ситуации, тем не менее, если требуется сократить число сообщений, отправленных в Скайп для бизнеса и группами Майкрософт пользователя. В таких случаях можно отключить отправку электронной почты.
  
Если отключить отправку сообщения электронной почты, аудиоконференций по электронной почте не будут отправлены для пользователей, в том числе по электронной почте для пользователей включены или отключены для аудиоконференций, когда сбросить свой ПИН-код, а идентификатор конференции и конференц-связи по умолчанию телефонный номер изменения .
  
Ниже приведен пример сообщений электронной почты, которое отправляется пользователям, когда они были включены для аудиоконференции:
  
![Звукового конференц-связи электронной почты](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Когда пользователи получают уведомления по электронной почте?

- Существует несколько сообщений электронной почты, отправленных для пользователей в вашей организации после их, необходимо включить для аудиоконференций.
    
  - Если для них назначена лицензия на **Аудиоконференции** .
    
  - При сбросе вручную аудиоконференций ПИН-код пользователя.
    
  - Выполнение сброса идентификатора конференции пользователя вручную.
    
  - При лицензии **Аудиоконференции** удаляется из них.
    
  - Поставщик услуг аудиоконференций пользователя изменении корпорацией Майкрософт на другой поставщик или **Нет**.
    
  - При изменении поставщика аудиоконференций пользователя в корпорацию Майкрософт.
    
## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Включение или отключение сообщением электронной почты, отправляемые пользователями

Скайп по центру администрирования Business или Windows PowerShell можно использовать для включения или отключения электронной почты для пользователей.
  
 **С помощью Скайп по центру администрирования бизнеса**
  
1. Sign in to Office 365 with your work or school account.
    
2. Перейдите в **Центр администрирования Office 365** > **Скайп для бизнеса**и на панели навигации слева щелкните **звук конференц-связи**.
    
3. На странице **параметров Microsoft моста** установите или снимите **автоматически отправлять сообщения электронной почты пользователям при их параметров аудиоконференций**.
    
4. Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.
    
    > [!TIP]
    > Можно также отправлять электронной почты для пользователя с помощью параметров аудиоконференций, перейдя на **аудиоконференции** > **пользователей**, выделите пользователя и нажмите кнопку **Отправить сведения о конференции по электронной почте**.  После этого, которая содержит только идентификатор конференции и конференции номер телефона, но не ПИН-код будет отправлено сообщение электронной почты.  [Отправить сообщение электронной почты для пользователя с помощью их сведения аудиоконференции](send-an-email-to-a-user-with-their-dial-in-information.md) более подробные сведения.
  
 **С помощью Windows PowerShell**
  
- Выполните следующие действия, чтобы отключить отправку сообщения электронной почты. 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    Справка с помощью этого командлета [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)см.
    
## <a name="what-else-should-you-know"></a>Дополнительные сведения

- При отключении автоматического по электронной почте может вручную активировать отправку сообщения электронной почты с конференции идентификатор и номер телефона с помощью Скайп по центру администрирования бизнеса. Тем не менее если этого ПИН-кода, не будут включены. Если требуется сбросить аудиоконференций ПИН-кода и отправка по электронной почте отключена, необходимо будет отправить его пользователю, с другой стороны.
    
- По умолчанию отправителя сообщения электронной почты будут из Office 365, но можно изменить адрес электронной почты и отображаемое имя, с помощью Windows PowerShell и также с помощью командлета [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) .
    
    > [!NOTE]
    >  Если вы хотите изменить сведения об адресе электронной почты, необходимо убедитесь в том, что политики входящей электронной почты в вашей среде разрешить сообщения электронной почты, полученные из настраиваемые указан адрес отправителя.
  
  - Введите отображаемое имя в параметр  _SendEmailFromDisplayName_.
    
  - Enter the email display name in the  _SendEmailFromDisplayName_ parameter.
    
  - Установите для параметра _SendEmailOverride_ значение _True_.
    
  -  `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
- Отключить отправку уведомлений по электронной почте можно в Центре администрирования Skype для бизнеса или с помощью Windows PowerShell.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Можно использовать эти командлеты для экономии времени или автоматизировать этот процесс.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах: 
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>See also

[Отправить пользователям при изменении их параметров звука конференц-связи по электронной почте](emails-sent-to-users-when-their-settings-change.md)

[Отправка пользователям электронных писем с информацией о конференции с телефонным подключением](send-an-email-to-a-user-with-their-dial-in-information.md)

[Настройка аудиоконференций в Skype для бизнеса и Microsoft Teams](set-up-audio-conferencing.md)

