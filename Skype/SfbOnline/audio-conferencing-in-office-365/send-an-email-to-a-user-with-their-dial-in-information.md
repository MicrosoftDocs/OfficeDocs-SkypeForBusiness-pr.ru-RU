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
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>Отправка электронного письма пользователю со сведениями о голосовой конференции в Skype для бизнеса Online

> [!Note]
> Сведения об отправке пользователям информации для участия в аудиоконференциях в Microsoft Teams см. в статье [Отправка пользователю сообщения электронной почты с информацией для участия в аудиоконференциях в Microsoft Teams](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams).

Sometimes Skype for Business users may need you to send them their Audio Conferencing information. You can do this by using the **Skype for Business admin center** and clicking **Send conference info via email** under the properties for a user. When you send this email, it will contain all of the audio conferencing information, including:
  
- Телефонный номер конференции или номер телефонного подключения для пользователя.
    
- Идентификатор конференции пользователя.
    
   
Ниже приведен пример отправляемого сообщения электронной почты.
  
![Сообщение о конференц-связи с телефонным подключением](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Отправка пользователю сообщения электронной почты с информацией для участия в аудиоконференциях

1. На панели навигации слева выберите пункт **Пользователи**, а затем выберите пользователя из списка доступных пользователей.

2. В верхней части страницы нажмите кнопку **изменить**.

3. В разделе **Аудиоконференции** щелкните **Отправить информацию для конференций в электронном письме**.

1. Войдите в свою рабочую или учебную учетную запись.
    
2. Перейдите в центр администрирования > **Skype для бизнеса**, а затем на панели навигации слева выберите пункт **звуковые конференции**.
    
3. Нажмите кнопку **Пользователи**, а затем выберите пользователя.
    
4. На панели действий щелкните **Отправить информацию о конференции по электронной почте**.
    
> [!TIP]
> Кроме того, вы можете отправлять электронную почту пользователю с помощью параметров конференц-связи, изменив свойства пользователя и **выбрав команду** > **отправить сведения о конференции по электронной почте**. 

## <a name="what-else-should-you-know-about-this-email"></a>Что еще необходимо знать о таких сообщениях?

- После включения поддержки голосовой конференции у пользователей вашей организации есть несколько сообщений электронной почты, которые отправляются пользователям.
    
  - При назначении пользователям лицензии **аудиоконференций**.
    
  - При ручном сбросе ПИН-кода голосовой конференции пользователя.
    
  - Выполнение сброса идентификатора конференции пользователя вручную.
    
  - При изъятии лицензии **аудиоконференций** у пользователя.
    
  - Когда поставщик видеоконференций для пользователя будет изменен с Microsoft на другого поставщика или **нет**.
    
  - После изменения поставщика голосовой конференции для пользователя на Microsoft.
    
- По умолчанию отправитель сообщений электронной почты отправляется из Microsoft 365 или Office 365, но вы можете изменить адрес электронной почты и отображаемое имя с помощью Windows PowerShell и командлета [Set-csonlinedialinconferencingtenantsettingshttp](https://go.microsoft.com/fwlink/?LinkId=708983) . Чтобы внести изменения в адрес электронной почты, который отправляет пользователям сообщение электронной почты, выполните указанные ниже действия.
    
  - Введите адрес электронной почты в параметре SendEmailFromAddress.
    
  - Присвойте параметру SendEmailOverride значение True.
    
  - Введите отображаемое имя электронной почты в параметре SendEmailFromDisplayName.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > Если вы хотите изменить адрес электронной почты, вам нужно убедиться, что политика входящих сообщений организации позволяет получать письма, отправленные с настроенного адреса электронной почты. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
    Чтобы отправить пользователю сообщение электронной почты со сведениями о голосовой конференции, выполните указанные ниже действия.
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- Когда речь идет о Windows PowerShell, Skype для бизнеса Online — это все, что нужно для управления пользователями и для пользователей, которым разрешено или не разрешено выполнять эти действия. С помощью Windows PowerShell можно управлять Microsoft 365 или Office 365, используя единую точку администрирования, которая позволяет упростить повседневную работу, если у вас есть несколько задач. Чтобы приступить к работе с Windows PowerShell, ознакомьтесь со следующими разделами:
    
  - [Зачем использовать Microsoft 365 или Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Microsoft 365 и Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности только при использовании центра администрирования Microsoft 365, например при одновременном изменении параметров для нескольких пользователей. Ознакомьтесь с этими преимуществами в указанных ниже разделах. 
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>См. также

[Попробуйте или купите голосовую конференцию в Microsoft 365 или Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
