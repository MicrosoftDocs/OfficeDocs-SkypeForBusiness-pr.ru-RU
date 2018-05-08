---
title: Отправить сообщение электронной почты для пользователя с помощью свои данные для подключения
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Отправьте сообщение электронной почты с их аудиоконференций сведения пользователей.
ms.openlocfilehash: da006b1e63dd36234acf20bb02fdffba2dc70fa2
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information"></a>Отправка пользователям электронных писем с информацией о конференции с телефонным подключением

В некоторых случаях Скайп для бизнеса или группами Майкрософт пользователей может потребоваться отправить их их аудиоконференции сведения. Это можно сделать с помощью **Скайп по центру администрирования бизнеса** , нажав кнопку **Отправить сведения о конференции по электронной почте** в разделе свойства для пользователя. При отправке это сообщение, он будет содержать все сведения аудиоконференций, включая:
  
- Телефонный номер конференции или номер телефонного подключения для пользователя.
    
- Идентификатор конференции пользователя.
    
   
Ниже приведен пример сообщения электронной почты:
  
![Сообщение о конференц-связи с телефонным подключением](../images/audio-conferencing-info.png)
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-send-an-email-with-audio-conferencing-information-to-a-user"></a>![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) Отправить сообщение электронной почты с информацией аудиоконференций для пользователя

1. Sign in to Office 365 with your work or school account.
    
2. Перейдите в **Центр администрирования Office 365** > **Скайп для бизнеса**и на панели навигации слева щелкните **звук конференц-связи**.
    
3. Щелкните **Пользователи**и затем выберите пользователя.
    
4. На панели действий щелкните **Отправить информацию о конференции по электронной почте**.
    
> [!TIP]
> Можно также отправить электронной почты для пользователя с помощью параметров аудиоконференций путем изменения свойства пользователя **аудиоконференции** > **отправлять сведения о конференции по электронной почте**. 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-you-know-about-this-email"></a>Что еще необходимо знать о таких сообщениях?

- Существует несколько сообщений электронной почты, отправленных для пользователей в вашей организации после их, необходимо включить для аудиоконференций.
    
  - Если для них назначена лицензия на **Аудиоконференции** .
    
  - При сбросе вручную аудиоконференций ПИН-код пользователя.
    
  - Выполнение сброса идентификатора конференции пользователя вручную.
    
  - Если лицензия на **Аудиоконференции** удаляется из их.
    
  - Поставщик услуг аудиоконференций для пользователя изменении корпорацией Майкрософт на другой поставщик или **Нет**.
    
  - При изменении поставщика аудиоконференций для пользователя в корпорацию Майкрософт.
    
- По умолчанию отправителя сообщения электронной почты будут из Office 365, но можно изменить адрес электронной почты и отображаемое имя с помощью командлета [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) и Windows PowerShell. Чтобы изменить адрес электронной почты, который отправляет сообщение электронной почты для пользователей, необходимо выполнить следующее:
    
  - Введите адрес электронной почты с помощью параметра SendEmailFromAddress.
    
  - Установите для параметра SendEmailOverride значение True.
    
  - Введите отображаемое имя электронной почты с помощью параметра SendEmailFromDisplayName.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > Если вы хотите изменить адрес электронной почты, вам нужно убедиться, что политика входящих сообщений организации позволяет получать письма, отправленные с настроенного адреса электронной почты. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
    Чтобы отправить сообщение электронной почты пользователя с их сведения аудиоконференций, выполните следующую команду:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

-  Что касается Windows PowerShell, то Skype для бизнеса online дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах: 
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>See also

[Пробная и платная аудиоконференции в Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
