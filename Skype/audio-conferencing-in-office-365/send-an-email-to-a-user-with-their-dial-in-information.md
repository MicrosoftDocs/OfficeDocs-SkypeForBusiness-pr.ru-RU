---
title: "Отправка пользователям электронных писем с информацией о конференции с телефонным подключением"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
description: "Send your users an email with their dial-in conferencing information."
---

# Отправка пользователям электронных писем с информацией о конференции с телефонным подключением

Иногда пользователям требуется, чтобы вы отправляли им информацию о конференциях с телефонным подключением. Вы можете сделать это из Центра администрирования Skype для бизнеса, нажав **Отправить информацию о конференции по электронной почте** в свойствах телефонного подключения для пользователя. При отправке этого электронного письма в нем будет содержаться следующая информация о телефонном подключении:
  
- Телефонный номер конференции или номер телефонного подключения для пользователя.
    
- Идентификатор конференции пользователя.
    
    > [!NOTE]
    > Статические идентификаторы используются, если люди в вашей организации не хотят запоминать случайные числа. Тогда они могут выбрать определенное число, которое проще запомнить. Если используются динамические идентификаторы конференции, каждое собрание, планируемое пользователем, получит уникальный идентификатор конференции. Если вы хотите назначить динамические, а не статические идентификаторы конференции, [Аудиоконференции с помощью динамических идентификаторы в вашей организации](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
Пример такого письма:
  
![Сообщение о конференц-связи с телефонным подключением](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## Отправка пользователям электронных писем с информацией о конференции с телефонным подключением

1. Войдите в Office 365 под своей учебной или рабочей учетной записью.
    
2. Перейдите в **Центр администрирования Office 365** > **Skype для бизнеса** и на левой панели навигации выберите **Конференц-связь с телефонным подключением**.
    
3. Щелкните **Подключенные пользователи** и затем выберите пользователя.
    
4. На панели действий щелкните **Отправить информацию о конференции по электронной почте**.
    
> [!TIP]
> Также можно отправить электронное письмо пользователю с помощью параметров конференц-связи с телефонным подключением, выбрав на странице свойств пользователя > **Конференц-связь с телефонным подключением** > **Отправить информацию о конференции по электронной почте**. 
  
## Что еще необходимо знать о таких сообщениях?

- Если пользователям разрешена конференц-связь с телефонным подключением, то электронные письма отправляются им в указанных ниже случаях:
    
  - Назначение лицензии на **Конференц-связь через ТСОП в Skype для бизнеса**
    
  - Выполнение сброса ПИН-кода конференц-связи с телефонным подключением пользователя вручную.
    
  - Выполнение сброса идентификатора конференции пользователя вручную.
    
  - Удаление лицензии на **Конференц-связь через ТСОП в Skype для бизнеса**
    
  - Изменение поставщика услуг конференц-связи с телефонным подключением с Microsoft на другого поставщика или на значение **Нет**.
    
  - Изменение поставщика услуг конференц-связи с телефонным подключением на Microsoft.
    
- По умолчанию отправитель электронных писем  Office 365, но вы можете изменить адрес электронной почты и отображаемое имя с помощью Windows PowerShell и командлета [Set-CsOnlineDialInConferencingTenantSettings](http://go.microsoft.com/fwlink/?LinkId=708983). Чтобы изменить адрес электронной почты, с которого выполняется отправка сообщений пользователям, выполните следующее:
    
    > [!NOTE]
    > Если вы хотите изменить адрес электронной почты, вам нужно убедиться, что политика входящих сообщений организации позволяет получать письма, отправленные с настроенного адреса электронной почты. 
  
  - Введите адрес электронной почты в параметр  _SendEmailFromAddress_.
    
  - Установите параметру  _SendEmailOverride_ значение _True_.
    
  - Введите отображаемое имя в параметр  _SendEmailFromDisplayName_.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
## Сведения по управлению с помощью Windows PowerShell

- Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688 ).
    
    Чтобы отправить пользователю электронное письмо с информацией о конференции с телефонным подключением, выполните следующее:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- Что касается Windows PowerShell, то Skype для бизнеса online дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](http://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](http://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Использование Windows PowerShell для управления Skype для бизнеса Online](http://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](http://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](http://go.microsoft.com/fwlink/?LinkId=294688). 
  

