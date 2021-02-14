---
title: Сброс ПИН-кода аудиоконференции в Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
description: 'Узнайте, что вам следует знать о ПИН-сах и как сбросить их в Skype для бизнеса Online. '
ms.openlocfilehash: 21e2742653e72919df0647c0539fdb335585cc84
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164698"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>Сброс ПИН-кода аудиоконференции в Skype для бизнеса Online

> [!Note]
> Информацию о сбросе ПИН-кодов аудиоконференций в Microsoft Teams см. в разделе [Сброс ПИН-кода аудиоконференций в Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).

A PIN is a code made up of numbers that is created for each Skype for Business user who is enabled for audio conferencing. Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone. If they use the Skype for Business app to start the meeting, a PIN isn't required. If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.
  
Meetings can be started when an authenticated user joins using the Skype for Business app or when the organizer joins with his or her PIN over the phone. When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts. If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.
  
## <a name="reset-a-users-pin"></a>Сброс ПИН-кода пользователя

1. Войте свою учетную запись с помощью своей учебной или учебной учетной записи.
    
2. Перейдите в Центр администрирования > **Skype** для бизнеса и на левой навигации щелкните "Аудиоконференция". 
    
3. Щелкните **"Пользователи"** и выберите пользователя, для который вы хотите сбросить ПИН-код.
    
4. На области действий в области **"ПИН-код"** нажмите кнопку **"Сброс".**
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Сброс ПИН-кода пользователем

A user can reset a PIN by using the **Reset PIN** option on the **Dial-in Conferencing** page. This page can be accessed in one of three ways:

* В браузере перейдите на страницу [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).
* В Skype для бизнеса нажмите стрелку **Показать меню** рядом с пунктом **Параметры**, затем нажмите **Средства** > **Параметры конференц-связи с телефонным подключением**.
* В Skype для бизнеса выберите **Параметры** и нажмите **Переадресация звонков** в меню слева, а затем в разделе **Дополнительные параметры вызовов** нажмите **Изменить параметры онлайн**. 

## <a name="what-else-should-you-know-about-pins"></a>Что еще необходимо знать о ПИН-кодах?

- For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset. After the PIN is reset by an administrator, the PIN will be listed as *********** in the **Skype for Business admin center** and in the results when they use Get-CsCsOnlineDialInConfencingUser in Windows PowerShell.
    
- Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.
    
- Когда начинается собрание, к нему автоматически присоединяются все пользователи, находящиеся в зале ожидания. Пример: если два участника попытаются присоединиться к собранию, когда оно еще не началось, эти участники будут перенаправлены в зал ожидания. Когда с телефона присоединяется организатор собрания под собственным ПИН-кодом, собрание начинается, и к нему подключаются все участники, находящиеся в зале ожидания.
    
- По умолчанию анонимные звонки не могут начать собрание.
    
- Если пользователю включена аудиоконференция, по умолчанию ему отправляются сообщения электронной почты, включающие данные для аудиоконференции и ПИН-код. У пользователя должен быть почтовый ящик Microsoft 365 или Office 365, так как при сбросе ПИН-кода новый ПИН-код отправляется пользователю по электронной почте на его основной SMTP-адрес (псевдоним), установленный для пользователя.
    
- When you set up audio conferencing, you set the digits that are required for the PINs in your organization. PINs can be from 4 to 12 digits - the default is 5. If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing. See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).
    
- По умолчанию для электронной почты устанавливается основной SMTP-адрес Microsoft 365 или Office 365 пользователя. Вы можете отправить сообщение электронной почты на адрес, не отправляемый на Microsoft 365 или не на office 365, например на Hotmail или MSN. Адрес электронной почты, заданный по умолчанию, можно Windows PowerShell. Это полезно, если у пользователей нет почтового ящика Exchange в Microsoft 365 или Office 365.
    
- To override the default user address where the email is sent, the tenant admin can use the following cmdlet: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com". The SendEmail parameter is required to override the email address of the user.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
- Чтобы задать ПИН-код для Amos Marble, выполните следующую команду:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell все о том, как управлять пользователями, а также о том, какие пользователи разрешены или не разрешены. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, см. указанные здесь разделы.
    
  - [Зачем нужно использовать Microsoft 365 или Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих темах:
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Статьи по теме

[Сброс идентификатора конференции для пользователя](reset-a-conference-id-for-a-user.md)
