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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Отправляйте своим пользователям сообщения электронной почты с информацией для участия в аудиоконференциях в Skype для бизнеса Online.
ms.openlocfilehash: 7b32608eae4fa5bb0d7f5b1eafbf49825ee937ad
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23849978"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>Отправка пользователю сообщения электронной почты с информацией для участия в аудиоконференциях в Skype для бизнеса Online

> [!Note]
> Сведения об отправке пользователям информации для участия в аудиоконференциях в Microsoft Teams см. в статье [Отправка пользователю сообщения электронной почты с информацией для участия в аудиоконференциях в Microsoft Teams](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams).

Иногда может потребоваться отправить пользователям Skype для бизнеса их информацию для участия в аудиоконференциях. Это можно сделать с помощью **центра администрирования Skype для бизнеса**, щелкнув в разделе свойств пользователя **Отправить информацию для конференций по электронной почте**. Это сообщение включает всю информацию для участия в аудиоконференциях, включая приведенные ниже данные.
  
- Номер конференц-связи или входящий телефонный номер пользователя.
    
- Идентификатор пользователя для участия в конференции.
    
   
Ниже приведен пример такого сообщения электронной почты.
  
![Сообщение о конференц-связи с телефонным подключением](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Отправка пользователю сообщения электронной почты с информацией для участия в аудиоконференциях

1. На левой панели навигации нажмите **Пользователи** и выберите пользователя в списке доступных пользователей.

2. В верхней части страницы нажмите **Изменить**.

3. В разделе **Аудиоконференции** щелкните **Отправить информацию для конференций в электронном письме**.

1. Войдите в Office 365 под своей учебной или рабочей учетной записью.
    
2. Выберите **центр администрирования Office 365** > **Skype для бизнеса** и в левой панели навигации щелкните **Аудиоконференции**.
    
3. Щелкните **Пользователи**, а затем выберите пользователя.
    
4. На панели действий щелкните **Отправить информацию для конференций по электронной почте**.
    
> [!TIP]
> Электронное письмо с параметрами аудиоконференций можно также отправить пользователю, отредактировав свойства пользователя и выбрав **Аудиоконференции** > **Отправить информацию для конференций по электронной почте**. 

## <a name="what-else-should-you-know-about-this-email"></a>Что еще необходимо знать о таких сообщениях?

- После того, как пользователям разрешено участие в аудиоконференциях, им отправляется несколько электронных писем.
    
  - При назначении пользователям лицензии **аудиоконференций**.
    
  - При ручном сбросе PIN-кода пользователя для участия в аудиоконференциях.
    
  - При ручном сбросе идентификатора пользователя для участия в конференциях.
    
  - При изъятии лицензии **аудиоконференций** у пользователя.
    
  - При изменении поставщика услуг аудиоконференций, отличного от Microsoft, или установке значения **Нет**.
    
  - При изменении поставщика услуг аудиоконференций обратно на Microsoft.
    
- По умолчанию отправителем сообщений является Office 365, но адрес электронной почты и отображаемое имя можно изменить с помощью Windows PowerShell и командлета [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983). Чтобы изменить адрес электронной почты, с которого пользователям отправляются письма, выполните следующие действия.
    
  - Введите адрес электронной почты в параметр SendEmailFromAddress.
    
  - Присвойте параметру SendEmailOverride значение True.
    
  - Введите отображаемое имя электронной почты в параметр SendEmailFromDisplayName.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > Если вы хотите изменить адрес электронной почты, вам нужно убедиться, что политика входящих сообщений организации позволяет получать письма, отправленные с настроенного адреса электронной почты. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
    Чтобы отправить пользователю электронное письмо с информацией для участия в аудиоконференциях, выполните следующие действия.
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

-  Что касается Windows PowerShell, то Skype для бизнеса online дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Почему следует использовать Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах: 
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Похожие темы

[Пробная и платная версия аудиоконференций в Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
