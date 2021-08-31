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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Отправляйте своим пользователям сообщения электронной почты с информацией для участия в аудиоконференциях в Skype для бизнеса Online.
ms.openlocfilehash: 428ff78fe501200ef9607a03d76c034007517cf0
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727678"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>Отправка электронного письма пользователю со сведениями об аудиоконференциях в Skype для бизнеса Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Сведения об отправке пользователям информации для участия в аудиоконференциях в Microsoft Teams см. в статье [Отправка пользователю сообщения электронной почты с информацией для участия в аудиоконференциях в Microsoft Teams](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams).

Иногда может потребоваться отправить пользователям Skype для бизнеса их информацию для участия в аудиоконференциях. Для этого в Центре  администрирования Skype для бизнеса и нажать отправить сведения о конференции по электронной почте в свойствах пользователя.  При отправке этого сообщения электронной почты оно будет содержать все сведения об аудиоконференциях, включая следующие:
  
- Телефонный номер конференции или номер телефонного подключения для пользователя.
    
- Идентификатор конференции пользователя.
    
   
Вот пример отправленного сообщения:
  
![Сообщение электронной почты для телефонной телефонии.](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Отправка пользователю сообщения электронной почты с информацией для участия в аудиоконференциях

1. В левой области навигации щелкните **Пользователи** и выберите пользователя из списка доступных пользователей.

2. В верхней части страницы нажмите кнопку **Изменить**.

3. В разделе **Аудиоконференции** щелкните **Отправить информацию для конференций в электронном письме**.

1. Во войти с помощью своей учебной или учебной учетной записи.
    
2. Перейдите в центр администрирования > **Skype для бизнеса** и в области навигации слева выберите аудиоконференцию . 
    
3. Щелкните **Пользователи** и выберите пользователя.
    
4. На панели действий щелкните **Отправить информацию о конференции по электронной почте**.
    
> [!TIP]
> Вы также можете отправить сообщение электронной почты пользователю с настройками аудиоконференции, отредактировать его свойства и щелкнуть Аудиоконференции Отправить сведения о конференции по электронной  >  **почте**. 

## <a name="what-else-should-you-know-about-this-email"></a>Что еще необходимо знать о таких сообщениях?

- После включения аудиоконференции пользователям в организации отправляется несколько сообщений электронной почты:
    
  - При назначении пользователям лицензии **аудиоконференций**.
    
  - При сбросе ПИН-кода аудиоконференции пользователя вручную.
    
  - Выполнение сброса идентификатора конференции пользователя вручную.
    
  - При изъятии лицензии **аудиоконференций** у пользователя.
    
  - При смене поставщика аудиоконференций для пользователя с Майкрософт на другого поставщика или **нет**.
    
  - При смене поставщика услуг аудиоконференций для пользователя на Майкрософт.
    
- По умолчанию отправитель сообщений отправляется из Microsoft 365 или Office 365, но вы можете изменить адрес электронной почты и отображаемого имени с помощью Windows PowerShell [и set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) Чтобы изменить адрес электронной почты, отправляемый пользователям, необходимо:
    
  - Введите адрес электронной почты в параметр SendEmailFromAddress.
    
  - Присвойте параметру SendEmailOverride значение True.
    
  - Введите отображаемое имя электронной почты в параметр SendEmailFromDisplayName.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > Если вы хотите изменить адрес электронной почты, вам нужно убедиться, что политика входящих сообщений организации позволяет получать письма, отправленные с настроенного адреса электронной почты. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).
    
    Чтобы отправить пользователю сообщение электронной почты со сведениями о аудиоконференции, запустите следующую функцию:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- Что касается Windows PowerShell, то Skype для бизнеса online дает возможность управлять пользователями, предоставляя им права на определенные действия. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единого администрирования, который упростит выполнение повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Зачем нужно использовать Microsoft 365 или Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центр администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах: 
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Использование Windows PowerShell для управления Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Статьи по теме

[Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
