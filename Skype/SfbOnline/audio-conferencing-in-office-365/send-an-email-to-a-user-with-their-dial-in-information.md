---
title: Отправка пользователю сообщения электронной почты с информацией для участия в аудиоконференциях в Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
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
description: Отправляйте своим пользователям сообщения электронной почты с информацией для участия в аудиоконференциях в Skype для бизнеса Online.
ms.openlocfilehash: f2137d05ebe588a316704fabf4c8878910a40bc0
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163906"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>Отправка пользователям электронных писем с информацией об аудиоконференции в Skype для бизнеса Online

> [!Note]
> Сведения об отправке пользователям информации для участия в аудиоконференциях в Microsoft Teams см. в статье [Отправка пользователю сообщения электронной почты с информацией для участия в аудиоконференциях в Microsoft Teams](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams).

Sometimes Skype for Business users may need you to send them their Audio Conferencing information. You can do this by using the **Skype for Business admin center** and clicking **Send conference info via email** under the properties for a user. When you send this email, it will contain all of the audio conferencing information, including:
  
- Телефонный номер конференции или номер телефонного подключения для пользователя.
    
- Идентификатор конференции пользователя.
    
   
Вот пример отправленного сообщения электронной почты:
  
![Сообщение о конференц-связи с телефонным подключением](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Отправка пользователю сообщения электронной почты с информацией для участия в аудиоконференциях

1. В области навигации слева **щелкните**"Пользователи" и выберите пользователя в списке доступных пользователей.

2. В верхней части страницы нажмите кнопку **"Изменить".**

3. В разделе **Аудиоконференции** щелкните **Отправить информацию для конференций в электронном письме**.

1. Войте свою учетную запись с помощью своей учебной или учебной учетной записи.
    
2. Перейдите в Центр администрирования > **Skype** для бизнеса и на левой навигации щелкните "Аудиоконференция". 
    
3. Щелкните **"Пользователи"** и выберите пользователя.
    
4. На панели действий щелкните **Отправить информацию о конференции по электронной почте**.
    
> [!TIP]
> Вы также можете отправить пользователю сообщение электронной почты с помощью параметров аудиоконференции, отредактировать его свойства и щелкнуть ссылку "Отправить сведения о конференции по электронной   >  почте". 

## <a name="what-else-should-you-know-about-this-email"></a>Что еще необходимо знать о таких сообщениях?

- После включения аудиоконференции пользователям в организации отправляется несколько сообщений электронной почты.
    
  - При назначении пользователям лицензии **аудиоконференций**.
    
  - При сбросе ПИН-кода аудиоконференции пользователя вручную.
    
  - Выполнение сброса идентификатора конференции пользователя вручную.
    
  - При изъятии лицензии **аудиоконференций** у пользователя.
    
  - При смене поставщика услуг аудиоконференций для пользователя с Microsoft на другого поставщика или **"Нет".**
    
  - При смене поставщика услуг аудиоконференций для пользователя на Майкрософт.
    
- По умолчанию отправитель сообщений отправляется из Microsoft 365 или Office 365, но вы можете изменить адрес электронной почты и отображаемого имени с помощью Windows PowerShell и [cmdlet Set-CsOnlineDialInConferencingTenantSettings.](https://go.microsoft.com/fwlink/?LinkId=708983) Чтобы изменить адрес электронной почты, отправляемый пользователям, необходимо:
    
  - Введите адрес электронной почты в параметр SendEmailFromAddress.
    
  - Присвойте параметру SendEmailOverride значение True.
    
  - Введите отображаемое имя электронной почты в параметр SendEmailFromDisplayName.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > Если вы хотите изменить адрес электронной почты, вам нужно убедиться, что политика входящих сообщений организации позволяет получать письма, отправленные с настроенного адреса электронной почты. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
    Чтобы отправить пользователю сообщение электронной почты со сведениями об аудиоконференции, запустите следующую функцию:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- Что касается Windows PowerShell, Skype для бизнеса Online позволяет управлять пользователями, а также управлять тем, что им разрешено или не разрешено. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, см. указанные здесь разделы.
    
  - [Зачем нужно использовать Microsoft 365 или Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих темах: 
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Статьи по теме

[Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
