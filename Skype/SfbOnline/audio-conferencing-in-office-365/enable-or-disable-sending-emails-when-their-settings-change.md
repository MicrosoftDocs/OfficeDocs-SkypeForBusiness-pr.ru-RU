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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Узнайте, как включать и отключать отправку писем с помощью Skype пользователям при изменении настроек, например ПИН-кода или номера для аудиоконференций по умолчанию. '
ms.openlocfilehash: 9deb04e418d00171375aec34ca873a89c8a31cdf
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011733"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>Включение и отключение отправки сообщений электронной почты при изменении параметров аудиоконференций в Skype для бизнеса Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Если необходимо включить или отключить отправку сообщений электронной почты в Microsoft Teams, см. статью [Включение и отключение отправки сообщений электронной почты при изменении параметров аудиоконференций в Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).

Пользователи автоматически получают уведомления по электронной почте, если они активированы для аудиоконференций. Однако иногда может потребоваться уменьшить количество сообщений электронной почты, отправленных Skype для бизнеса пользователям. В этом случае можно отключить функцию отправки сообщений по электронной почте.
  
Если отключить отправку сообщений электронной почты, электронные письма для аудиоконференции не будут отправляться пользователям, включая сообщения о том, когда пользователи включены или отключены для аудиоконференции, при сбросе ПИН-кода, а также при смене кода конференции и номера телефона конференц-связи по умолчанию.
  
Вот пример сообщения электронной почты, которое отправляется пользователям, если для них включена аудиоконференция:
  
![Электронная почта для аудиоконференций.](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Когда пользователи получают уведомления по электронной почте?

- После включения аудиоконференции пользователям в организации отправляется несколько сообщений электронной почты.
    
  - При назначении пользователям лицензии **аудиоконференций**.
    
  - При сбросе ПИН-кода аудиоконференции пользователя вручную.
    
  - Выполнение сброса идентификатора конференции пользователя вручную.
    
  - Если удаляется лицензия  **Аудиоконференции**.
    
  - При смене поставщика услуг аудиоконференций пользователя с Microsoft на другого поставщика или **нет**.
    
  - При смене поставщика услуг аудиоконференций пользователя на Майкрософт.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Включить или отключить отправку электронной почты пользователям

Вы можете использовать центр администрирования Skype для бизнеса или Windows PowerShell, чтобы включить или отключить электронную почту, отправленную пользователям.

 
![Значок с логотипом Skype для бизнеса логотипом.](../images/sfb-logo-30x30.png) **Использование центра Skype для бизнеса администрирования**
    
1. В центре **Skype для бизнеса администрирования** на левой навигации щелкните Аудиоконференция. 
    
2. На странице **Параметры моста Microsoft** поставьте или снимите флажок **Автоматически отправлять сообщения пользователям при изменении их параметров аудиоконференций**.
    
3. Нажмите кнопку **Сохранить**.
    
    > [!TIP]
    > Можно также отправить сообщение электронной почты с параметрами аудиоконференции пользователю, выбрав **Аудиоконференции** > **Пользователи**, выбрав пользователя и нажав **Отправить сведения о конференции по электронной почте**.  В этом случае будет отправлено сообщение электронной почты, которое содержит только код конференции и номер телефона конференции, но не ПИН-код.  Дополнительные [сведения см.](send-an-email-to-a-user-with-their-dial-in-information.md) в статьи Отправка пользователю сообщения электронной почты со сведениями об аудиоконференциях.
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Использование Windows PowerShell**
  
- Для отключения отправки сообщений электронной почты выполните следующие действия. 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    См. справку относительно этого командлета: [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings).
    
## <a name="what-else-should-you-know"></a>Дополнительные сведения

- Если автоматическая отправка электронной почты отключена, вы по-прежнему можете вручную запускать отправку сообщения электронной почты с помощью ИД конференции и номера телефона, используя Skype для бизнеса центре администрирования. Однако в этом случае ПИН-код не будет включен. Если вы хотите сбросить ПИН-код аудиоконференции и отправка сообщений электронной почты отключена, необходимо отправить его пользователю другим способом.
    
- Отключить отправку уведомлений по электронной почте можно в Центре администрирования Skype для бизнеса или с помощью Windows PowerShell.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Можно использовать эти командлеты для экономии времени или автоматизировать этот процесс.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Remove-CsOnlineDialInConferencingTenantSettings)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](/powershell/module/skype/Get-CsOnlineDialinConferencingTenantConfiguration)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единого администрирования, который упростит выполнение повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Зачем нужна Microsoft 365 или Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центр администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах: 
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-битных компьютерах, можно скачать из Центра загрузки Майкрософт по ссылке Загрузка и установить [модуль Teams PowerShell](https://go.microsoft.com/fwlink/?LinkId=294688)(.). /set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md).
  
## <a name="related-topics"></a>См. также

[Сообщения электронной почты, отправленные пользователям при изменении параметров аудиоконференции](emails-sent-to-users-when-their-settings-change.md)

[Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции](send-an-email-to-a-user-with-their-dial-in-information.md)
