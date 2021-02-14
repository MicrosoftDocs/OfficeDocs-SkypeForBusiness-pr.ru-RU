---
title: Включение и отключение отправки сообщений электронной почты при изменении параметров аудиоконференций в Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Узнайте, как включать и отключать отправку писем с помощью Skype пользователям при изменении настроек, например ПИН-кода или номера для аудиоконференций по умолчанию. '
ms.openlocfilehash: 681a02fd410c008f46ad7906c5963660df668a89
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164268"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>Включение и отключение отправки сообщений электронной почты при изменении параметров аудиоконференций в Skype для бизнеса Online

> [!Note]
> Если необходимо включить или отключить отправку сообщений электронной почты в Microsoft Teams, см. статью [Включение и отключение отправки сообщений электронной почты при изменении параметров аудиоконференций в Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).

Users are automatically notified by email when they are enabled for Audio Conferencing. There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users. In such cases, you can disable sending email.
  
Если отключить отправку сообщений электронной почты, электронные сообщения для аудиоконференции не будут отправляться пользователям, включая сообщения электронной почты о том, когда пользователи включены или отключены для аудиоконференции, когда сбрасывается ПИН-код, а также когда изменяется код конференции и номер телефона конференц-связи по умолчанию.
  
Вот пример сообщения электронной почты, которое отправляется пользователям, если для них включена аудиоконференция:
  
![Сообщение электронной почты относительно аудиоконференции](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Когда пользователи получают уведомления по электронной почте?

- После включения аудиоконференции пользователям в организации отправляется несколько сообщений электронной почты.
    
  - Если пользователям назначена лицензия **Аудиоконференции**.
    
  - При сбросе ПИН-кода аудиоконференции пользователя вручную.
    
  - Выполнение сброса идентификатора конференции пользователя вручную.
    
  - Если удаляется лицензия  **Аудиоконференции**.
    
  - При смене поставщика услуг аудиоконференций для пользователя с Microsoft на другого поставщика или на **"Нет".**
    
  - При смене поставщика услуг аудиоконференций пользователя на Майкрософт.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Включить или отключить отправку электронной почты пользователям

Вы можете использовать Центр администрирования Skype для бизнеса или Windows PowerShell, чтобы включить или отключить электронную почту, отключаемую для пользователей.

 
![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**
    
1. В Центре **администрирования Skype** для бизнеса на левой навигации щелкните **"Аудиоконференция".**
    
2. На странице **Параметры моста Microsoft** поставьте или снимите флажок **Автоматически отправлять сообщения пользователям при изменении их параметров аудиоконференций**.
    
3. Щелкните **Сохранить**.
    
    > [!TIP]
    > You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.  If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.  See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Использование Windows PowerShell**
  
- Для отключения отправки сообщений электронной почты выполните следующие действия. 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    См. справку относительно этого командлета: [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
## <a name="what-else-should-you-know"></a>Дополнительные сведения

- When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center. However, if you do this, the PIN won't be included. If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.
    
- Отключить отправку уведомлений по электронной почте можно в Центре администрирования Skype для бизнеса или с помощью Windows PowerShell.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Можно использовать эти командлеты для экономии времени или автоматизировать этот процесс.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- Windows PowerShell все о том, как управлять пользователями, а также о том, какие пользователи разрешены или не разрешены. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, см. указанные здесь разделы.
    
  - [Зачем нужно использовать Microsoft 365 или Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих темах: 
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Статьи по теме

[Сообщения электронной почты, отправленные пользователям при изменении параметров аудиоконференции](emails-sent-to-users-when-their-settings-change.md)

[Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции](send-an-email-to-a-user-with-their-dial-in-information.md)


